## Crear e instalar (en IIS) certificado SSL autofirmado

A continuación ser muestran todos los pasos necesarios para realizar la solicitud e instalación de un certificado de seguridad SSL autofirmado (self-sign). Para ello se hará uso de la terminal de Windows 10 (PowerShell) con permisos de administrador para poder ejecutar una serie de comandos. Asimismo, se configuraron algunos detalles en cuanto a los certificados de usuario.


Antes de ejecutar los comandos es importante crear una carpeta o directorio en donde se van a guardar todos los archivos que se van creando. Por eso una vez se abra la terminal hay que situarse dentro de la carpeta creada. Una vez explicado lo anterior, se procederá a explicar cada comando.


## Generación del certificado root

Comando: 

```
openssl genrsa -des3 -out rootCA.key 2048
``` 

Explicación:

- **openssl:** herramienta necesaria para los certificados de seguridad.

- **genrsa:** indica que se creará una llave con encriptado RSA.

- **des3:** algoritmo de encriptado DES (triple).

- **out rootCA.key:** indica el nombre del archivo que se exportará.

- **2048:** longitud de la llave en bits.

Al ejecutar el comando el sistema solicitará la creación de una contraseña para el certificado root.

Siguiente comando: 

```
openssl req -x509 -new -nodes -key rootCA.key -sha256 -days 1024 -out rootCA.pem
``` 

Explicación:

- **req -x509:** especifica el tipo de solicitud.

- **-new**: crea una nueva solicitud.

- **-nodes:** indica que el archivo de salida no se encriptará.

- **-key:** indica el archivo que tendrá una clave privada.

- **-sha256:** algoritmo de cifrado.

- **-days:** cantidad de días de validez del certificado.

- **-out**: indica que se escribirán los cambios en el archivo de salida designado.

Una vez ejecutado el comando, solicitará la contraseña creada en el paso anterior y además requerirá de ciertos datos para el certificado, tales como: nombre del país, ciudad, organización, entre otros.


## Creación del certificado SSL

Para comenzar con la creación del certificado SSL se debe crear un archivo con el siguiente nombre: <code>v3.ext</code>.

Dentro de este archivo se debe insertar la siguiente información:

```
authorityKeyIdentifier=keyid,issuer
basicConstraints=CA:FALSE
keyUsage = digitalSignature, nonRepudiation, keyEncipherment, dataEncipherment
subjectAltName = @alt_names
[alt_names]
DNS.1 = www.tusitioweb.com
``` 

**Explicación**: este archivo permitirá asignar a un dominio los atributos para el certificado de seguridad. La parte importante acá es colocar el o los dominios que funcionarán con este certificado, en este ejemplo solo se utilizó uno, pero perfectamente se pueden asignar varios de la siguiente manera:

```
DNS.2 = www.undominio.com
DNS.3 = www.otrodominio.com
``` 

### Creación y firma de la solicitud del certificado SSL


```
openssl req -new -nodes -out server.csr -newkey rsa:2048 -keyout server.key
``` 

Nuevamente se solicitarán algunos datos como país, cuidad, organización, etc.


### Generación final del certificado SSL

```
openssl x509 -req -in server.csr -CA rootCA.pem -CAkey rootCA.key -CAcreateserial -
out server.crt -days 500 -sha256 -extfile v3.ext
``` 

Con el comando anterior todos los archivos quedarán relacionados entre sí y solamente quedaría seguir unos pasos extra para preparar el certificado para poder se usado dentro de IIS.


## Preparación del certificado SSL para importarse a IIS

Para poder utilizar un certificado de seguridad SSL en IIS se debe utilizar un archivo con la extensión <code>.pfx</code>, necesario para poder instalarse en el sitio web que se creó con anterioridad.

### Creación del archivo .pfx


```
openssl pkcs12 -inkey server.key -in server.crt -export -out server.pfx
```

Cuando este comando es ejecutado solicitará una contraseña para ser exportado, es muy importante recordar la contraseña que se ingrese, ya que IIS la solicitará a la hora de ser importada.


## Configuración del administrador de certificados de usuario


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1611180603093/e5UO_EnBz.png)

Una vez en el administrador de certificados de usuario se debe seguir la ruta:

<code>Personal → Certificados</code>


En certificados se debe hacer click derecho y seleccionar «todas las tareas o all tasks» e importar los siguientes archivos de la carpeta que se creó al inicio:

1. rootCA.pem
2. server.pfx

Luego dentro del mismo administrador de certificados de usuario de debe localizar la carpeta «Trusted Root Certification Authorities» y realizar los mismos pasos que se hicieron anteriormente, es decir: 

<code>certificados → click derecho → todas las tareas o all tasks</code> e importar el archivo <code>rootCA.pem</code>.

Al importar el archivo anterior aparecerá una ventana de advertencia, a la cual se le debe dar que «SÍ»


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1611180715370/iVc377-UQ.png)


## Importando el certificado SSL a IIS

El primer paso es abrir IIS y seleccionar la opción de los certificados del servidor.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1611180759125/YitURTjMU.png)

Luego en la parte derecha seleccionar «importar».


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1611180802735/MI_nrRpW4.png)

Luego aparecerá una ventana en la que hay que buscar el archivo .pfx que se creó anteriormente, además de la contraseña que se le asignó al archivo. Los últimos campos se pueden dejar con los valores por defecto.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1611180824473/d5vwoM1NY.png)

Una vez importado el certificado de seguridad se debe seleccionar el sitio web al que se le instalará el certificado, para luego seleccionar la opción de <code>bindings</code>, tal y como se muestra en seguida:


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1611180847452/r5KccBCQN.png)

Ya estando en «bindings» se deben colocar algunos datos y seleccionar el certificado SSL que se creó.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1611180874520/Fu6A94AWE.png)

Es importante colocar en tipo <code>HTTPS</code> y colocar la URL del sitio web en el Host Name. Y ya con esto el certificado estaría instalado correctamente y puede ser probado en cualquier navegador.
En este caso se utilizó Firefox Developer Edition en su versión 84.0b8, navegador que se debe configurar para evitar las advertencias de sitio no seguro.


## Configurando Firefox

Para permitir el certificado creado dentro del navegador se debe seguir la siguiente
ruta:

<code>menú → opciones → seguridad y privacidad → ver certificados</code>


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1611180939296/UsaL9pqjJ.png)

Luego se abrirá una ventana que es el administrador de certificados y bajo la pestaña de «Authorities» se debe importar el archivo <code>rootCA.pem</code>.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1611180967504/zkQA7HQE7.png)

Finalmente aparecerá la siguiente ventana en la que se debe marcar la primera opción:

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1611180991690/tVKbYspDd.png)

Y eso sería todo. En navegadores basados en Chromium podría presentar advertencias sobre el certificado, pero solventar ese problema quedaría para otro post.




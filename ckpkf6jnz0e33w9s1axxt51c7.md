## Text to handwriting | Python

Hi, guys, these days I was playing a little with <code>pywhatkit</code> library, you know, the one I used in [this post](https://jeffcoding.com/enviar-mensajes-de-whatsapp-desde-python) to send WhatsApp messages from Python. The point is that I came across with this pywhatkit's feature really, really interesting, as you can see in the title the function I am talking about is: convert text to hand written characters.

# pywhatkit library

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1622932644224/WDGe_TiSe.png)

Pywhatkit is Python library with some great features, such as: sending WhatsApp messages at certain time, Google searching, converting images to ASCII, sending emails,  among others features.

## Requirements

First things first, you have to install pywhatkit library, so you have to open your command prompt and  enter this pip command:

<code>pip install pywhatkit</code>

After that you can now import the library as following:

<code>import pywhatkit as pw</code>

I used **pw** to create an alias to the library, but you can name it as you want.

>In some cases you will have to install <code>python3-tk</code> along with pywhatkit

 
## Parameters

We need 3 parameters (2 optional) to make it work.

* the text you want to convert to handwriting text.
* save_to (optional): the path you want to save the image.
* rgb (optional): color of the handwriting text in rgb format.

## Example

Now we are able to try this feature.

Here's the code:


```python
import pywhatkit as pw

txt = "jeffcoding.com"

pw.text_to_handwriting(txt, "image.png")
``` 

## Result



![image2.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1622934765059/bG9Yy6-_C.png)

---

If you want to know the other features deeply you can [click here](https://pypi.org/project/pywhatkit/)

That's all for now, if I missed something let me know in the comments.
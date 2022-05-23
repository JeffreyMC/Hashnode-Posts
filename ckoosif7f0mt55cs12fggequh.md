## Default parameters | JavaScript

So this is my first post in English, It was a friend of mine's idea because my last post receive more engagement and I thought it was because the last post's cover had a text in English, so here I am, let's see how it goes.

As you may know, JavaScript introduced default parameters in functions since ECMAScript 2015's version. This is a great feature and I am going to show you how it works, it's pretty simple.

Let's suppose we have a function that shows the result of adding two numbers.

```JavaScript
const add = (a, b) => {
        return a + b
} 

console.log(add(3, 5))

// Result = 8
``` 
Now, let's add another parameter to the function. What happens if by mistake I enter just two values instead of three, just like this:

```JavaScript
const add = (a, b, c) => {
        return a + b + c
} 

console.log(add(3, 5))

// Result = NaN
```
The console is showing that error because the parameter **c** is not defined. Here is when default paramaters comes on the stage.

# Default parameters

If we give a default value to the parameter **c** the function will work, even if we don't give it a value when we call it.

```JavaScript
const add = (a, b, c = 5) => {
        return a + b + c
} 

console.log(add(3, 5))

// Result = 13
```

In the example above I gave to the parameter **c** the value of 5, so when I called the function the result was 13 (3 + 5 + **5**). Now, what happens if I call the function but I give a value to the third parameter? 

```JavaScript
const add = (a, b, c = 5) => {
        return a + b + c
} 

console.log(add(3, 5, 2))

// Result = 10
```

In the example above the default parameter didn't work because I gave it a value (2) when I called the function. Default parameters works when for some reason you don't give it a value when calling the function, on purpose or not. 

The last example shows what happens if you have set default parameters in a function but you want to give a null value to one of them.

```JavaScript
const add = (a = 2, b = 4, c = 5) => {
        return a + b + c
} 

console.log(add(3, null, 2))

// Result = 5
```
As you can see, If I give to a parameter a **null** value, the default parameter's value will be ignored.
___
I hope this little trick helps you. See you next time.

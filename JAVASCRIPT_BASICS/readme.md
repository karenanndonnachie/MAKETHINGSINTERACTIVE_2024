# Getting started with Javascript 


### What is Javascript?


Javascript is the programming language of the internet. It is what makes websites interactive.

There are implementations of Javascript that run in lots of different environments (like node.js, for the console, or versions that live inside of game engines). There are also a lot of frameworks and libraries that extend its functionality (for example- p5.js). These are useful things to keep in mind as tools for future projects! But we’ll be using plain old Javascript- often called ‘vanilla’ Javascript.

We are using this because it is hard to underestimate the reach of JS in 2022. Using it also means that you can immediately publish your work as an interactive website.

A nice thing about JS is there isn’t an installation. You already have a working and up-to-date version with any modern browser. I’ll be demoing in Firefox, but Chrome is essentially identical in functionality.

For those that know anything about HTML and CSS, Javascript is the last bit of that puzzle. HTML is the "content" of the web (static content on websites). CSS is the "styling". Javascript is the "interaction".

### Why would we need javascript? (We are working with Arduino...)
Javascript can play very well with all Iot projects, can interact with most APIs, and can even run Arduino directly when Arduino is flahed with "Firmata" which means that you can use all the groovy NLP, computer vision, sound libraries of p5js directly or indirectly in your interactive arduino projects. 

**Adding Javacript to your HTML page **


If you’ve done this before, the structure of a website will look familiar to you.

```
<!DOCTYPE html>

<script>

javascript goes here

</script>

<style>

css goes here

</style>

<html>

        <head>

                <title>this is what is displayed in the webpage’s title bar</title>

        </head>

        <body>

this is the content of the page

        </body>

</html>
```

You can place JS directly between script tags, like this:

```
<script>

javascript goes here

</script>
```

Or have it search for an external JS page, like this:

```
<script src="yourfile.js"></script>
```

I prefer the second, as it is cleaner. But both are valid.


# HTML/CSS/JavaScript

So, now we've learnt how to be code borrowers and rescuers (ahem), we should start figuring out some code of our own. We will start with the basic trifecta - hyper-text markup language, or html; cascading style sheets, or css; and javascript, or js. These coding languages are often found interacting together on webpages - we've already seen them in our last few studios - and they each have a special role.

**HTML**
HTML is the scaffold, if you like, of a webpage, the architecture or infrastructure. It tells you what is what and in relation to what.

**CSS**
CSS is the artist, the designer. It tells you what colour things should be or how they should be laid out.

**JavaScript**
.js is the gymnast, making things move and change. It adds interactivity like clicks and pop-ups.

For those of you who are familiar with web development, feel free to let your hair down and have fun. For those new to coding, we're going to learn to wrangle the basics of html/css/java, and figure out how to make our own webpage, rather than stealing someone else's!.

> #### Being tricksy!
>
>So, there are two ways of dealing with this trifecta of codes: the good, honorable and strategic way; and the lazy way. We're going to learn the lazy way because there is a time and a place for lazy code - but you need will to know how to do it the more complicated way if you ever decide to make a fancy multi-page website. It means separating out your css and javascript into separate documents, and pointing to them in your <header> tag.

## 1. Create a webpage.

Create a new folder in your computer called studio3.

Open Atom on your computer.

Select File > New File. Then select File > Save. Navigate to your `studio3` folder, and call your file `index.html.` Press "Save."

Congrats! You now have a website.

## 2. Set up HTML.

Let's play with some HTML and get some of the basic elements down.

Firstly, we have to let any program reading the file what type it is - so let's declare it. Copy and paste the below code (or type it out!) onto the top of your `index.html` page:

``` HTML
<!DOCTYPE html>
```
 You can select Packages > Preview HTML now if you'd like. It should work and help you going forward.

 So, html works on a series of tags that open and close like this `<tag> </tag>`

We need to let the script reader know what is parts are html. So, let's put in a tag like this:
``` html
<html>

</html>
```
 Everything between these tags is html.

Now, inside the html tag, we're going to separate out two more subsections: `<head>` which is where all the metadata goes and `<body>` which forms the bulk of the page.

``` HTML
<head>

</head>
<body>

</body>
```
So, your code will look something like this:
``` html
<!DOCTYPE html>
<html>
<head>

</head>
<body>

</body>
</html>
```
## Add some content

Right-o. Let's add some more content. In `<head>`, add a `<title>` tag to give your webpage a name, and specify that we're using the UTF-8 character set:
``` HTML
<title> BEST HTML PAGE EVER! </title>
<meta charset="UTF-8">
```
And now, in the body, add some lovely text! You can use different levels for text inclusion:
``` html
<h1>This is a Heading</h1>
<p>This is a paragraph.</p>
```  
> (This is a great resource if you get stuck: https://www.w3schools.com/html/html_intro.asp)

And, let's embed an video as well! Go to YouTube, find a video (I've chosen nyan cat), and in the "Share" section, copy the embed `<iframe>` code:
``` html
<iframe width="560" height="315" src="https://www.youtube.com/embed/2yJgwwDcgV8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```
> pay attention here! These tag is important for putting your future projects on your github website. You can embed pretty much anything as long as you specify the type: <embed> for general; <img> for images; <iframe> for html - see more here: https://www.w3schools.com/tags/tag_embed.asp
 
Finally, add some links to your other studio pages.

```html
<a href="https://cwilmott.github.io/website/studio1.html">Studio 1</a> <!--- You need to change this bit to match your webpage --->
```
Try to do Studio 2 on your own!

Your code will look something like this now:

```html
<!DOCTYPE html>
<html>
<head>
  <title> BEST HTML PAGE EVER! </title>
  <meta charset="UTF-8">
</head>
<body>
  <h1>This is a Heading</h1>
  <p>This is a paragraph.</p>
  <iframe width="560" height="315" src="https://www.youtube.com/embed/2yJgwwDcgV8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
 <a href="https://cwilmott.github.io/website/studio1.html">Studio 1</a><a href="https://cwilmott.github.io/website/studio2.html">Studio 2</a>
</body>
</html>
```
 ## Set up your css

 Now, we need to create a CSS within the html document. In the `<head>` tag, create a `<style></style>` tag. This is where we will put our CSS. Now, in the `<style>` tag copy and paste the following code:
 ``` css
body {background-color: powderblue}
h1 {color: red; text-align: center;}
p {font-family: verdana; font-size: 20px; text-align: right;}
```
Drag your index.html folder into a browser window and see what happens!

> the html <tags> need to match the css to work! More info here: https://www.w3schools.com/css/default.asp

## JavaScript it up!

Okay, so as a very quick JavaScript tutorial, we're going to make what's called a **function** which changes the css of your text, and then trigger it using an **event**

All the things that you can do in JavaScript have names - like functions, objects, strings, events, variables - and it's useful to learn these vocabularies if you're interested in going deeper into JS programming.

Doing internal js in a html document is pretty easy - you just need to let the program reading it know what parts are in javascript using the `<script>` tag.

### 1. Create the thing that you want to be affected by the script and give it a name.
In the `<body>`, write the following code:

```` html
<p id="change"> Watch me change! </p>
````

 This is a simple way of giving a name (or "id") to a specific section.

### 2. Write a function to explain how something the thing should be changed

 Now, we need to make a `<script>` section:
 ```` html
<script>
</script>
````
Let's write a (java) script to create the change. I'll put `//comments` in the script so you know what's happening.

 ``` JavaScript
function changeCSS (){
  document.getElementById("change").style.color = "red"; //document find "change" and make it red
}
```

Try on your own to add another style change to the "changeCSS" function! And then, paste it in the `<script>` section.

### 4. Create an event to trigger your function!

So, now we're going to make a button click "event" that triggers our function `changeCSS` above.

In the `<body>` but after the close `</script>` tag, write the following button with an "onclick" event:
```
<button type="button" onclick="changeCSS()">Click here!</button>
```
So, your total code will look something like this:
``` html
<!DOCTYPE html>
<html>
<head>
  <title> BEST HTML PAGE EVER! </title>
  <meta charset="UTF-8">
  <style>
    body {background-color: powderblue}
    h1 {color: red; text-align: center;}
    p {font-family: verdana; font-size: 20px; text-align: right;}
  </style>
</head>
<body>
  <h1>This is a Heading</h1>
  <p>This is a paragraph.</p>
  <iframe width="560" height="315" src="https://www.youtube.com/embed/2yJgwwDcgV8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
  <p id="change"> Watch me change! </p>
  <script>
  function changeCSS() {
    document.getElementById("change").style.color = "red";
  }
  </script>
  <button type="button" onclick="changeCSS()">Click here!</button>
</body>
</html>
```
Click **save** and drag your index.html file into your browser, and see if it works!

> at this point, go to https://www.w3schools.com/ and start having some fun! Play around and make stuff. If it's not working, check out the tips for debugging in the .studios github folder.

## Upload!

Finally, in order to make your map work for everyone, you need to put your files on a server.

To do this, we're going to upload your key files to Github using the github.io repository you made in Studio 1.

Go to https://github.com/ and login.

On the left, select your github.io repository (mine is cwilmott/website) (this is because I have to have a separate one for the studios)

This will bring up the folder for your repository.

Select "Add File" and then "Create New File". Call it `index.html`

Navigate to your html file in Atom and copy and paste the code into the github code editor.

Then press "Commit Changes"

Now, if you go to another browser - or the same browser - and type in the name of your github.io repository ending in studio3.html (it's the bit in bold in the folder section, so, mine is https://cwilmott.github.io/website/) then you should see your nifty webpage live and online! 

*Don't forget to post the link to the #studios Slack channel!*

You can now use this as a base page for navigating to your various studios, building a portfolio or anything you want!

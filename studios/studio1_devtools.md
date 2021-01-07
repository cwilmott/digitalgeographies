## DevTools

> This Studio requires you to have the browser Google Chrome installed, and to have set up your GitHub Pages account.

Developer Tools, or DevTools address are in-browser tools made for wed developers to debug websites and monitor and maintain their performance. They are also excellent tools for us to crack the surface of websites and get a sense of what they're made of - including different advertising elements, data caching and tracking, links, server hosts etc...

Most browsers have the capacity to help you do this in some way - even if it is simply saving the page as a web source, and opening it in a code editor like Atom (we are going to learn how to do this at the end of the studio when we run off with someone else's web page). But we're going to use Chrome because the tools in-browser are a little more obvious to see and more interactive. 

#### 1. Take a look through the Developer Tools

Open *Chrome* and navigate to a webpage of your choice - preferably one whose code you don't mind mildly and temporarily appropriating at the end of the studio. I've chosen www.theguardian.com.

There are a few ways of opening DevTools. 

At the far right of the address bar, there are three small dots in a vertical pattern. Click on them, then scroll down to 'More Tools' and then select 'Developer Tools' . This will open up the general DevTools panel.

If you're interested in a particular section, you can right-click on it and select "Inspect".

Take some time to have a play around and explore the different sections across the top of the page. If you find words or functions that you don't understand, look them up! 

*Elements* - Elements maps the different parts of the webpage, usually scaffolded in html.

*Sources* - Sources is useful for seeing where different elements come from, and which third party services are being used. 

*Application* - Application details the database saves, including the SQL, cookies and application cache.

*Network* - Network shows what the website is doing in real time, including data being uploaded, transferred and downloaded, data requests and the response from the system.  

More documentation on DevTools can be found here: https://developers.google.com/web/tools/chrome-devtools

#### 2. View, download and upload the page source

So, now we are going to get a sense of what pulls a page together, and download some of the information. 

Right-click on your webpage and select "View Page Source". This will bring up a new tab with a bunch of code that [really should] start with:
`<!DOCTYPE html>`. Take a look at the code. What's going on? What patterns can you see between the website and the page source? Can you see any common words? Try picking a text word at random from the webpage, and hitting control or command F and searching for it on the page. 

Next, we are going to download the code. There are a bunch of different ways we can do this. A web page is just a file, like a word document or spreadsheet. You can either:
1. right-click on the web page, select "Save as", and download it as a .html only webpage, called "studio1.html";
2. go to Atom - your code editor - and choose File -> New File (or ctrl/cmd N). Then, back on your webpage, select ctrl/cmd A to select all the code, copy it and paste it into your new Atom file. Then save it as a "studio1.html" 
3. go directly to your GitHub pages repository, create a new file called "studio1.html" and copy and paste the code in there. 

If you've chosen option 1 or 2, you'll need to then upload your file to your GitHub Pages repository. 

#### 3. Change some stuff, acknowledge copyright, and bask in your licentiousness.

Now, we're going to check that your new webpage works. It may not - most web pages have hundreds of links to other pages, images, databases and files. Some of these links are "static" or absolute, meaning that the path to those files is not relational - they are hosted on the internet and have a full stable web address starting (usually) with https. If there are gaps, or breakages, or missing bits and pieces, it may be that the code is referencing parts of the website which have relative paths (i.e. are in the same folder), or are hidden from the public. Don't worry - now you know what they're trying to hide!

On GitHub Pages, find and select your file. Click the little pen icon to edit, and a box will appear where you can change the code.

We're going to do a few little things, just to get you comfortable with some coding, and because it's funny.

**Change the content of a tag**

HTML files are structured using things called "tags" or `<misc> ... </misc>`, or . These tags have pretty self explanatory names about what they're doing - some are technically important, some are aesthetic, some link to other bits and pieces. We'll go into this in more depth during the HTML/CSS/JS studio. 

For now, in the `<head>` section, I want you to find a tag called `<title>`. This tag tells the web browser what the webpage is called and what should appear in the tab or at the top of the browser page. On theguardian.com/us it looks like this:

``` HTML
<title>News, sport and opinion from the Guardian's US edition | The Guardian</title>
```

Not touching either the opening `<title>` or closing `</title>` tags, change the title of your webpage to something else. Mine now reads:

``` HTML
<title>Dropped the "Manchester", moved to London</title>
```

**Add a comment**

The second and last thing we're going to do is add a comment. Comments are ways that developers use to make notes in the text of code, without affecting the code itself or appearing on the webpage. At the top of the source code of theguardian.com/us is a large (and hilarious!) comment advertising jobs for digital web developers. 

Comments in different coding languages have different formatting. In HTML, they are enclosed in the following `<!-- COMMENT!-->`  

Under the `<head>` opening tag, write a comment that looks something like this: 

``` HTML
<!-- copyright [your website]! Borrowed briefly. -->
```

**Commit your changes and share with us!**

Now, at the bottom of the page select "Commit Changes". It can take a few minutes (or longer) for the changes to be updated on the GitHub Server, but go to your webpage - `[yourname].github.io/digitalgeographies/studio1.html` and check to see if it has updated.

When it has - or even before - post your link to the #studios channel on the Slack. 

#### Well done! 
 

## archive.org
#### (or, the internet doesn't forget)

In this studio, we're going to be working with the Internet Archive, which is an incredible online repository of old internet materials including software, websites and other historical internet materials (based over the bay in SF!). It serves a few purposes:
- to flesh out some of the archival practices of old digital technologies in line with the reading by Ernst;
- to continue to familiarise ourselves with digital structures and systems through a deep dive into the internet past;
- and, possibly most importantly, to also re-encounter the alt-history of digital geographies, the internet, technology and space using these skills.

### 1. Get familiar

To start, in **Chrome** go to: https://archive.org

Take a look around. Find some cool stuff. Have fun. Be a nerd.

To download a document - either a video, book, audio file etc... - on the bottom right of the page it will say **download options**, just choose a file type and download it.  

### 2. Play with an emulator

One of the hardest things about preserving digital or computational histories is the relationship between hardware and software - just because you have an old floppy disk, doesn't mean that you have the machine that can read it. Ernst goes through a range of different ways that archives like the Internet Archive work around this issue - and one of the best features of internet.org is that they have built-in emulators which mimic the original operating systems of old hardware so you can play old games and applications *on your own computer!*

On the top menus, choose **Software**.

In the drop-down, choose MS-DOS Games, Classic PC Games, Historical Software Collection or another option (it's more fun if it's game-based). I have chosen --> Historical Software --> Lemonade Stand (1979).

Click the middle button (that looks like a power-on button), and this will start up the emulator. Play your game! Remember, most old games were keyboard-oriented (not mouse), so you'll need to use your keys!

When you're done, post a screenshot of your game along with:
- its title
- its year
- the original operating system (OS) (i.e Apple, )
- the metadata "topics" + language.
- and the emulator that the archive.org is using to play it (in the metadata at the bottom of the description)

### 3. Dig up an old website on Wayback Machine

Now we've had some fun, and had a little look at how emulators function, we're going to do a little work.

**ubp.com**

To begin, in a fresh page on your browser, go to: http://ubp.com/

Yes - this is the webpage for Union Bancaire Privée (UBP), some Swiss investment bank. *But* this is a pretty famous URL, back in the day.

**Wayback Machine**

Now, return to archive.org, and select "WEB" or click in the Wayback Machine search bar and type or paste in http://upb.com/

A calendar will popup with a bar graph visualisation at the top, and circles on individual days. This shows a list of impressions, or "snapshots" of the website on the date and time that they were taken, from the earliest to the most recent, from the Alexa Internet crawl data (https://archive.org/details/alexacrawls). Its linked to the URL (i.e. the bit that starts http), not the content of the webpage, so it's really useful for seeing how webpages have changed over time; what the headline was on yahoo news on Sept 11 2001; that blog post that someone thought they might have deleted. Like most archives, it's not totally complete - but rather a fragmented collection of moments throughout the life of a URL.

*Choose a year, 1998 - 2000*. Then choose a day with a circle on it, and select the impression (you need to click on the timestamp on the popup menu).

Welcome to http://ubp.com/, the Universal Black Pages, an early African-American web directory. Some info here (https://www.africa.upenn.edu/Acad_Research/bgsa_glbl.html) and here (https://archive.nytimes.com/www.nytimes.com/library/tech/98/10/circuits/library/08libe.html)

Take another look around. Not all the webpages will work - you might need to copy and paste the URL for individual pages (i.e. http://ubp.com/about/) back into the Wayback Machine and find another snapshot.  

Then, when you're ready, return to the main home page.

### 4. Download and clean the page   

So, this final studio section, we're going to download the UBP homepage, and upload it to our github.io website.

**Download complete webpage**

This is a bit like last week, but also a little different. Remember how in the last studio we learnt how websites are made up of heaps of different links to different files like images, pages, fonts, code libraries etc....? And how we copied and pasted the code from our website into a fresh page and it mostly just worked (maybe...), because all of the files and pages and links were already online and had absolute addresses? This isn't the case for this - because the URL is being used by a new (super capitalist) website, so any links or images will point to that page, not ours, and the webpage probably won't find them.

So, what we're going to do is right-click on the UBP page, and choose, "Save Page As" (or similar). Choose the format "Webpage, complete", save it somewhere safe, and press "Save".

In your save folder, you will have two files:
- The Universal Black Pages.htm
- The Universal Black Pages_files

Rather than just downloading the html code, this download also downloads all of the associated files in a folder.

**Tidy**

Open up the `The Universal Black Pages.htm` file in **Atom**, your code editor.

Have a read of the code, paying attention to the comments. Can you find the name of someone who worked on the page?

Before we upload to github.io, we're going to take out some of the Wayback Machine paraphernalia.

Find this section:

```HTML
<!-- BEGIN WAYBACK TOOLBAR INSERT -->
<style type="text/css">
body {
  margin-top:0 !important;
  padding-top:0 !important;
  /*min-width:800px !important;*/
}
</style>
<script>__wm.rw(0);</script>
<div id="wm-ipp-base" lang="en" style="display: block; direction: ltr;">
</div><div id="donato" style="position:relative;width:100%;">
  <div id="donato-base">
    <iframe id="donato-if" src="./The Universal Black Pages_files/donate.html" scrolling="no" frameborder="0" style="width:100%; height:100%">
    </iframe>
  </div>
</div><script type="text/javascript">
__wm.bt(650,27,25,2,"web","http://www.ubp.com/","19990125104114",1996,"/_static/",["/_static/css/banner-styles.css?v=bsmaklHF","/_static/css/iconochive.css?v=qtvMKcIJ"]);
  __wm.rw(1);
</script>
<!-- END WAYBACK TOOLBAR INSERT -->
```
Select it, and delete it.

Save it, and drag `The Universal Black Pages.htm` file into Chrome. The webpage should appear, without the Wayback Machine Toolbar.


### 5. Put it back in the present (sort-of)

Now, return to your github.io pages repository.

Create a new file called studio2.htm . Copy and paste the code from your Atom file into your github file. Then, in the studio2 folder, select `Upload` and upload `The Universal Black Pages_files` folder.

Now, test your webpage works! And remember to copy and paste it into the #studio Slack channel as a comment under your game screenshot!

### Well done!

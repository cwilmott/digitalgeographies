## Tables: CSV + JSON

Today, we're going to do some basic data table hacking. Hopefully, this will give us an idea about the specifically spatial relationships between different kinds of data and data structures.

 We are going to be working with a couple of different kinds of data formats:
- JSON (or JavaScript Object Notation)
- CSV (or comma-separated values)
- HTML tables

These skills can be used for any kind of data, as long as you know what you're working with. If you're a data scientist, or familiar with these skills, feel free to go wild with your analysis! For those of us mortals, let's just stick with these three.

### 1. Sign in to Google Drive/Sheets

First things first, sign into your Google Drive account using your berkeley.edu login.

Go to Google Sheets and open a new blank sheet and name it **"studio5"**

In Google Sheets (as with most spreadsheet software), each workbook is comprised of tabs called sheets. You can create new tabs by clicking the small `+` button at the bottom-left of the page, and clicking on the tab to rename it:

![](https://i.stack.imgur.com/ElXSV.png)

Name your first sheet **"Input"**

### 2. Locate Data

Now we're going to locate the data that we need. I've chosen a random topic that has been bothering me, which is the amount of money college football coaches are paid each year.

I've found a few sources of data which can help us explore this topic.

1. First of all, we need a **list of all the colleges in the US** so that we can make sure all our colleges are called the same thing across all of our sheets. For instance, different data sources might call Berkeley, UCB or UC Berkeley, or Cal, or University of California, Berkeley, or just Berkeley, which digital text processors read as being different places - you need human context (or a database that I can't find!) to know that they're the same! I've found this super helpful database of US Post-Secondary institutions by Kiersten Hudson: https://hifld-geoplatform.opendata.arcgis.com/datasets/colleges-and-universities?geometry=57.798%2C-16.798%2C-57.163%2C72.130
2. We also need a **list of top salaries for US college football coaches**. USA Today provides a yearly list here: https://sports.usatoday.com/ncaa/salaries/football/coach, and assistant coaches here: https://sports.usatoday.com/ncaa/salaries/football/assistant
3. And for some flavour, I've found this NBC database which shows ***the fees students pay for college athletics***, and what percentage of the total athletics budgets are supported by these fees: https://www.nbcnews.com/news/education/hidden-figures-college-students-may-be-paying-thousands-athletic-fees-n1145171. This one is a bit of a pain to scrape, so I've already done it and saved it as a CSV here: https://github.com/cwilmott/digitalgeographies/blob/main/studios/studio4/NCAADiv1_Financing.csv   

Create three columns in your Inputs sheet with the following headings:

| Name | Owner | Source |
|------|-------|--------|
|      |       |        |

Then, note the details and paste your links in:

| Name       | Owner           | Source                                                                                                                        |
|------------|-----------------|-------------------------------------------------------------------------------------------------------------------------------|
| Colleges   | Kiersten Hudson | https://hifld-geoplatform.opendata.arcgis.com/datasets/colleges-and-universities?geometry=57.798%2C-16.798%2C-57.163%2C72.130 |
| Coaches    | USA Today       | https://sports.usatoday.com/ncaa/salaries/football/coach                                                                      |
| Assistants | USA Today       | https://sports.usatoday.com/ncaa/salaries/football/assistant/assistant                                                                          |
| Fees       | NBC             | https://github.com/cwilmott/digitalgeographies/blob/main/studios/studio3/NCAADiv1_Financing.csv                               |


### 3. Import into Google Sheets

Now we're going to drag our data into Google Sheets so that we can work with it! And we'll do it a little backwards so that we can start easy and work up to harder.

We're going to use a range of `IMPORT` functions available via Google Sheets, including `IMPORTDATA`, `IMPORTHTML` and `IMPORTXML`.

>IMPORTXML: Imports data from any of various structured data types including XML, HTML, CSV, TSV, and RSS and ATOM XML feeds.
>IMPORTRANGE: Imports a range of cells from a specified spreadsheet.
>IMPORTHTML: Imports data from a table or list within an HTML page.
>IMPORTFEED: Imports a RSS or ATOM feed
>IMPORTDATA: Imports data at a given url in .csv (comma-separated value) or .tsv (tab-separated value) format.
>
>For more info on how to use these functions, see: https://support.google.com/docs/answer/3093335?hl=en&ref_topic=9199554


**Fees** (IMPORTDATA)
- Create a new sheet and call it "fees"
- Return to the Github file (https://github.com/cwilmott/digitalgeographies/blob/main/studios/studio3/NCAADiv1_Financing.csv) and select `raw`. This will give you a raw page of comma-separated values - copy the `raw` address (https://raw.githubusercontent.com/cwilmott/digitalgeographies/main/studios/studio3/NCAADiv1_Financing.csv).
- Now, return to your "fees" Google Sheets.
- Click the top right corner to select all cells.
- In the formula bar, write the following function with the formula: `=IMPORTDATA("raw_data_link")` so that it looks like this:
```
=IMPORTDATA("https://raw.githubusercontent.com/cwilmott/digitalgeographies/main/studios/studio3/NCAADiv1_Financing.csv")
```
The data should populate across the sheet.

**Coaches** (IMPORTHTML)
- Create two new sheets and call them "coaches" and "assistants"
- As before, select the top corner so all the cells are selected.
- Now, we're going to build a little formula. Rather than the neatly packaged .csv format that we found in the `fees`, we're going to pull the data straight from the html page. If you right-click and inspect the the table, you'll see where it sits on the page as an embedded `<table>` class. So, this makes it pretty easy: the `IMPORTHTML` has three parameters - the address, the HTML class, and which number on the page it is. In this case, it's https://sports.usatoday.com/ncaa/salaries/, table and 1. So, our `=IMPORTHTML("link","class", number)` formula will look like this:
```
=IMPORTHTML("https://sports.usatoday.com/ncaa/salaries/","table",1)
```

**Assistants** (IMPORTHTML)
- Now, try the above steps on your own for the assistants salaries!

**Colleges** (IMPORTXML)
- Okay, so last and ugliest (but coolest), IMPORTXML and the colleges list.
- Go to the colleges page - https://hifld-geoplatform.opendata.arcgis.com/datasets/colleges-and-universities?geometry=57.798%2C-16.798%2C-57.163%2C72.130.
- We could just download the whole dataset as a spreadsheet, but it's messy. Instead, select the API Explorer tab. This allows us to Query the database and import it.
- We don't need all these "Out Fields", so let's cull it down to the `Name`, and `Zip` data (so we can geocode if we'd like).


> TOP TIP! In the Google Chrome Dev Tools, if you right-click on a piece of html you can select Copy > Full XPath if you need to!

- Salaries
- Fees
- Locations



### 4. Clean Data

This is the most arduous and essential part of data management. Much can be automated (when dealing with large data sets), but much also just relies on going through the data and tidying it up.

Change all the titles of your sheets to "Input-(SheetTitle)" (i.e. Input-Fees), because we're importing the data, any changes we make aren't going to be reflected. Then, create a set of new sheets with the old names - Fees, Coaches, Assistants. Select all the data, copy and then in the new sheet, select Edit > Paste Special > Paste Values Only.

**Get rid of weird text and symbols**
So, the Fees page has a bunch of weird asterixes and they're annoying me. You can use the Edit > Find and Replace, so find * and replace with nothing. Make sure you specify the sheet!

**Get rid of annoying columns**
We don't need the Rk columns in Coaches and Assistants, so delete them.

**Make the College names match**
Another issue is that the colleges use different naming conventions between the USA Today and NBC data sets. We need to make them match so we can join them together later on. Normally, you'd have a master name list but this is just a studio and we're going to be a little lazy.
- First, rename the "Schools" column to "College" in "Coaches" and "Assistants".
- We'll use the NBC conventions because they're more complete. The range for this list is `Fees!A:A`.
- Go to your Coaches sheet. Then select Data > Data Validation. The Cell range is `Coaches!A:A` and the validation criteria is matched against the Fees sheet, "List from a range" `Fees!A:A`. Select "Show Warning" and "Show Validation Help text", which should be "Click and enter a value from range Fees!A:A". Then hit **save**.
- Now the boring part of going through and picking the correct university for each option. If you're not sure which campus, look it up. If there isn't a match, delete it.
- Do the same for the Assistant coaches. There are way more, so I only kept the top 200 or so. If you're keen, you can do all 650.
- Finally, counter validate the fees names against the coaches, so there aren't any stray fees without coaching salaries. Delete all that don't have a pair.  
> If you have time, I'd recommend going through it yourself since it's good practice and gives you a good sense of how the data tables work. It takes about 30 mins. BUT, because I care, I've also pre-made you a cleaned list here: https://docs.google.com/spreadsheets/d/1FzWH8Ss9fP9rGvGuqAJA2KPbqm3y6fEcl4nbWtKvw_o/edit?usp=sharing - which you can copy and paste in.

### 5. Visualise Data!

The final step today - so we don't just close our eyes and see tables - is to visualise this data. I'd personally normally use Tableau's free public account (or you can get a free student account), but I want to minimise the number of pieces of software I ask you to download, so we're going to try the Google Data Studio
Explorer beta.

Sign in to your Berkeley Google Drive and then to Google Data Studio (in Chrome): https://datastudio.google.com

### Link Data

Select `Create` and choose **Data Source**. Then select "Google Sheets". Choose **studio5**, and then one of the cleaned sheets. I chose Fees. *You can only choose one sheet per data source*.

Then click `Connect`.

In the connection, make sure the type of data matches the data "type". You may need to switch the number to "currency". I like to switch place names to "Geo - Address".

### Muck around with visualization

Next, go to Create - Explorer.

Start buy having a play around with some of the Fees data with different visualisations.

### Table Join

Next, we will try to "blend data", which is better known as a "table join", where we join two or more tables based on a shared column.

Click on blend data, and join your data sets with the college join link. It can be a little buggy, but if it's not working, click on different visualisations and see how you go.

And then just play around with the software. See what you can do!

## 6. Save and share.

For your final part, we're going to share your data.

When you have a vis you're either happy with or bored with your visualisation, click "Save" on the top right.

Then click "Share". Create a new report, and at the top, you'll find a URL embed code, or you can retrieve it from the Share menu.

Go to **Atom** and create a new file. Then click Save-As and call it 'studio4.html'.

You now need to do the basics to build a HTML file that we learnt last week. Copy and paste the below in the file:

```` html
<!DOCTYPE html>
<html>
<head>
  <title>Studio 4</title>
  <meta charset="UTF-8">
</head>
<body>
<!-- paste embed code iframe here -->

</body>
</html>
````
Now, return to your report and embed code. Make sure it's the size you want (but you can also change this later) and copy it.

Paste it into your `studio4.html` document in the `<body>`. Check it works on Preview HTML.

Finally, go to Github Pages, where your index.html page is.

Click **Add File** then **Create New File**. Name it `studio4.html`, and copy and paste the code from Atom into the page.

Commit the changes. And copy the file path starting with https://

And to end, return to your index.html page and let's put a link in so we can access the page from the main website.

Copy and paste the file path code, somewhere that you're happy for a link to be in the body:

``` html
<a href="link_to_path">Studio 4</a>
```

And then commit changes.

And don't forget to post your link to the #studios Slack!

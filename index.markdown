---
title: Google Refine for Investigative Journalism (NICAR 2012/Dan Nguyen)
---
<head>
<style>
    body {
      font-size: 14px;
      line-height: 22px;
      font-family: "Helvetica Neue", Helvetica, Arial;
		width: 900px;
		margin: auto auto;
		background: #eee;
    }

	.container{

	}
	
	div.imgwrap{
		width: 100%;
		text-align: center;
		margin-bottom: 2.0em;
	}
	
	div.imgwrap img{
		margin: auto auto;
		border: thin solid #777;
	}
  
    a img {
      border: 0;
    }
    h1, h2, h3, h4, h5, h6 {
      padding-top: 20px;
    }
      h2 {
        font-size: 22px;
      }
    b.header {
      font-size: 18px;
      line-height: 35px;
    }
    span.alias {
      font-size: 14px;
      font-style: italic;
      margin-left: 20px;
    }
    table {
      margin: 15px 0 0; padding: 0;
    }
      tr, td {
        margin: 0; padding: 0;
      }
        td {
          padding: 0px 15px 5px 0;
        }
    code, pre, tt {
      font-family: Monaco, Consolas, "Lucida Console", monospace;
      font-size: 12px;
      line-height: 18px;
      font-style: normal;
    }
      tt {
        padding: 0px 3px;
        background: #fff;
        border: 1px solid #ddd;
        zoom: 1;
      }
      code {
        margin-left: 20px;
      }
      pre {
        font-size: 12px;
        padding: 2px 0 2px 15px;
        border: 4px solid #bbb; border-top: 0; border-bottom: 0;
        margin: 0px 0 25px;
      }
    
  </style>
</head>


# Google Refine for Investigative Journalism

*An introduction to one of the best data tools for any reporter of any technical level*


This is a hands-on walkthrough for [NICAR 2012](http://www.ire.org/conferences/nicar-2012/). It will take place on **Friday**, from **2 &ndash; 2:50PM** in the **Jeffersonian/Knickerbocker** room. It will be led by Dan Nguyen ([@dancow](http://twitter.com/dancow)) with help from Joe Kokenge ([@josephkokenge](http://twitter.com/josephkokenge)) of ProPublica.

You'll learn some of the basic (yet very powerful) features and we'll even do some examples of interesting journalism. No statistics, programming, or Excel skill required. Watch the [official video tutorials here](http://code.google.com/p/google-refine/). Read [my tutorial I wrote showing how Refine was essential](http://www.propublica.org/nerds/item/using-google-refine-for-data-cleaning "Chapter 1. Using Google Refine to Clean Messy Data - ProPublica") in our award-winning [Dollars for Docs investigation](http://projects.propublica.org/docdollars/) at ProPublica.

 

<div class="imgwrap">
<img alt="Obama in 3D" title="Obama in 3D" src="images/3d-obama.jpg">

	<img alt="A screenshot of Refine" title="A screenshot of Refine" src="images/grefine-wh-visitors.png">

	<div class="caption">Let's find out who's been going to the <a href="http://www.whitehouse.gov/briefing-room/disclosures/visitor-records" title="Visitor Access Records | The White House">White House the past few years</a>...</div>
</div>


## A tool for cleaning and investigations

[Google Refine](http://code.google.com/p/google-refine/) is called: "a power tool for working with messy data" 

If you haven't tried Refine yet, then you're missing out on the potential stories and insights that Refine can easily (and sometimes exclusively) find in data. 

It doesn't matter what skill level you have. Refine, which works right out of your browser (and offline) is one of those unique tools that is as equally useful to those who have never left their click-and-drag interfaces as it is to the most anal-retentive detail-oriented data analysts and command-line-loving power programmers.

In this lesson, I'll start at the very basics: opening a file with Refine, doing basic sorting, searching (things that you can do in Excel, of course) to its easy-to-use data cleaning methods and then to how Refine can help you probe unfamiliar datasets to scout out a story.


### The Dilemma 
There are, of course, about an unlimited number of ways that a dataset will do its best to raise your blood pressure. The two situations I'll cover are:

* You pretty much know exactly what you're trying to find but you have no idea how messy/dirty the data is and if it's even cleanable

* You don't even really know what's in the data or what you should be doing with it. You just want a really easy way to explore it.


### The Data
The two datasets I will be working with are:

* [FEC Individual Contribution Data](http://www.fec.gov/finance/disclosure/ftpdet.shtml#a2011_2012) &ndash; the list of citizens who have individually contributed $200+ to the political process

* The [White House Visitor Logs](http://www.whitehouse.gov/briefing-room/disclosures/visitor-records) &ndash; everyone who has visited the White House during the Obama Administration (in the time period it chose to disclose), who they visited, and (sometimes) why.

(hopefully we'll have time to do both)


## Contacts

* Dan Nguyen ([@dancow](http://twitter.com/dancow))
* Joseph Kokenge ([@josephkokenge](http://twitter.com/josephkokenge))







# The FEC Data

*This tip sheet is a work-in-progress...I will be filling it out through today and it should be done by the time of my hands-on session*

The Federal Election Commission [posts datafiles](http://www.fec.gov/finance/disclosure/ftpdet.shtml "Download Detailed Files by Election Cycle") containing every federal political contribution from  **individuals** in which the **amounts are over $200**.

The fields included are: *"the ID number of the committee receiving the contribution, the __name, city, state, zip code, and place of business__ of the contributor along with __the date and amount__ of the contribution. NOTE: this file can be very large file."*

### What we hope to find
There are some obvious inquiries here. If you're curious about the total for **all** of the individuals, then you don't need Refine for that. You can just put this in Excel/Access and do the usual SUM equation.

However, if you want to do something [like you've seen at OpenSecrets](http://www.opensecrets.org/politicians/contrib.php?cycle=2012&amp;cid=N00003675&amp;type=I ": Campaign Finance/Money - Top Donors -  2012 | OpenSecrets"), which purports to show total amount donated by individuals from a certain company or industry, then you're going to need Refine to get you to the point where you make use of this data in Excel.


### Loading the data
Open the Google Refine application, which will either automatically open up a new browser window or tell you to point your browser to this address (this is a local address on your computer): **127.0.0.1:3333**

Click the **Create Project** tab:

<div class="imgwrap">
	<img alt=" " title=" " src="images/fec-001-create.png">
	<div class="caption"></div>
</div>


This will prompt you to point your browser to a data-file. As you can see, it supports a variety of formats, including CSV and Excel spreadsheets.

The [data-file](https://github.com/dannguyen/NICAR-Google-Refine/blob/master/data/fec/itcont-2012-MONY.txt.zip?raw=true) that I've prepared for this hands-on session has been re-formatted to be **tab-delimited** and I've pre-filtered it to **include only Missouri and New York donors in 2012**.

Download it here:
[https://github.com/dannguyen/NICAR-Google-Refine/blob/master/data/fec/itcont-2012-MONY.txt.zip?raw=true](https://github.com/dannguyen/NICAR-Google-Refine/blob/master/data/fec/itcont-2012-MONY.txt.zip?raw=true)


The next screen in Refine is a preview of the data. There's not much to do here as Refine is pretty good at knowing whatever you gave it by default. Click **Create Project** in the top right to continue.

<div class="imgwrap">
	<img alt=" " title=" " src="images/fec-002-preview.png">
	<div class="caption"></div>
</div>



### The basic stuff (sorting, filtering)

To get familiar with how spreadsheet/Google-doc'ish Refine is, let's start with concepts you probably already know: **sorting** a spreadsheet by a column and **filtering** by value.

To **sort** a column, simply click on the **down-arrow** by the column you want. 

Let's start with the **state**, or as the FEC calls it, **ITEM-ST**:

<div class="imgwrap">
	<img alt=" " title=" " src="images/fec-010-sort.png">
	<div class="caption"></div>
</div>




# The White House Visitor Logs
*This tip sheet is a work-in-progress...I will be filling it out through today and it should be done by the time of my hands-on session*

### Background material

<!--
<div class="imgwrap">
	<img alt=" " title=" " src="images/">
	<div class="caption"></div>
</div>
-->
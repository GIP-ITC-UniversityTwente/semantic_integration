---
layout: default
title:  "Semantic Integration 2019"
---

<link href='https://cdn.jsdelivr.net/npm/yasgui@2.7.29/dist/yasgui.min.css' rel='stylesheet' type='text/css'/>
<script src='https://cdn.jsdelivr.net/npm/yasgui@2.7.29/dist/yasgui.min.js'></script>
<img src="tut1.png" alt="Linked Data">


## Content
---
1. [About Linked Data](about_LD.md)
2. [Assignment 1](SI_1.md)
3. [Assignment 2])(ST_2.md)

## Introduction

In this tutorial you will learn how to create Linked Data representation of a simple table using ontologies.
The source for conversion is a table in a *.csv format. With the help of the tool this CSV-file will be converted into Linked Data.

**Comma-separated values (CSV)** is a widespread format for spreadsheets and simple databases.
It uses plain text to store tabular data. Each record consists of one or more fields (columns),
separated by commas. This format is not standardized, but the idea to separate values using an agreed
upon delimiter is very simple. There are many variants including tab-separated values and
space-separated values.

Therefore, first of all, we need a table.


### Step 0: Let's make a table

Bellow is a simple **CSV** table that lists names of 2 persons together with their age and places of birth.
In **CSV** this looks very simple:

```csv
Name,Age,Place of birth
Neil,33,Enschede
Leelah,15,Utrecht
```

You can copy the example from above and paste it in a text file. Or just [download it](https://1drv.ms/u/s!Ah2_2X7uyAX5iNhG5jxgU27tPh19Bw)

And this is a rendered version:

| Name | Age | Place of birth |
| ---- | --- | -------------- |
| Neil | 33 | Enschede |
| Leelah | 15 | Utrecht |

This data will be converted into Linked Data following the logic of the 4 design principles.
 
## Install GraphDB

## Create the data
 
  <div id='yasgui'></div>
  <script type="text/javascript">
      var yasgui = YASGUI(document.getElementById("yasgui"), {
          //Uncomment below to change the default endpoint
          //Note: If you've already opened the YASGUI page before, you should first clear your
          //local-storage cache before you will see the changes taking effect
          //yasqe:{sparql:{endpoint:'bla'}}
      });
  </script> 



---
layout: page
title:  "Tutorial: Load LTB Data"
subtitle: "exploration of Linked Data"
---

---------------

## Content
---
- [Load LTB Data](#ltb)
  - [Step 1. Download the content of a study area as RDF](#step1)
  - [Step 2. Change file extension](#step2)
  - [Step 3. Create a new repository](#step3)
  - [Step 4. Upload the data into the repository](#step4)
  - [Step 5. Explore your data.](#step5)

--------------

## Load LTB Data   <a name="ltb"></a>

Before we can start the tutorial we need to obtain the data and to upload it into the triplestore.  
We will use data from the LivingTextbook, namely data from your study areas. 
Therefore, the first step is to download an RDF-version of your study area data. 

- **Step 1.**  <a name="step1"></a> Download the content of a study area as RDF. Go to the dashboard of your study area and click ***Data*** -> ***Export*** . After that, on the download page you 
will be able to specify the required ***Export type*** as ***RDF (JSON-LD)*** . [JSON-LD](https://json-ld.org/) is 
one of the formats used for serialising RDF data. Other example formats 
are [RDF/XML](https://www.w3.org/TR/rdf-syntax-grammar/), [Turtle](https://www.w3.org/TR/turtle/), 
[N-triples](https://www.w3.org/TR/n-triples/) etc. Click the ***Export*** button to start downloading. 

- **Step 2.**  <a name="step2"></a> Change file extension. The downloaded file has **.json** extension. Before it can be loaded into GraphDB, the extension
 needs to be changed to **.jsonld** . Rename the file, so it is **.jsonld** .
 
- **Step 3.** <a name="step3"></a>  Create a new repository. Create a new repository with repository ID *ltb*. [See instructions on how to...](http://graphdb.ontotext.com/documentation/8.9/free/quick-start-guide.html#create-a-repository).

- **Step 4.**  <a name="step4"></a> Upload the data into the repository. Make sure that *"ltb"* is your active repository. Then click ***Import*** -> ***RDF***. 
Chose ***Upload rdf Files***  and provide the path to the your JSON-LD file that has extension **.jsonld**
 
 - **Step 5.**   <a name="step5"></a> Explore your data. When the importing is finished you can explore your LTB data using 
 GraphDB Exploration interface. For example, you can see that you have 3 classes in you LTB data by 
 clicking ***Explore*** -> ***Class relationships*** .
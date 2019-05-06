---
layout: page
title:  "Requirements"
subtitle: "before you start"
---

Tutorials and assignments of this course require installation of some tools 
to recreate a common architecture of Linked Data applications. 

---------------

## Content
---
- [1. Architecture](#arch)
- [2. Backend: Triplesore](#backend)
  - [2.1 Installation of GraphDB](#graphdb)
  - [2.2 Test the installation](#test)
  - [2.3 Allow requests from other domains](#cors)
- [3. Frontend](#frontend)
  - [3.1 YASGUI: Yet Another Sparql GUI](#yasgui)
  - [3.2 Sparklis](#sparklis)

---------------


## 1. Architecture <a name="arch"></a>
This architecture is depicted in the figure below. 

## 2. Backend: Triplesore. <a name="backend"></a>
Databases built for the storage and retrieval of triples using semantic queries are called triplestores. 
The list of existing implementation is quite impressive and includes about 50 different solutions. 
For tutorial we will install and use **[GraphDB](https://www.ontotext.com/products/graphdb/)**, 
developed by [Ontotext](https://www.ontotext.com/), because it has: 
- a lovely Graphical User Interface
- a support of [geoSPARQL](http://graphdb.ontotext.com/documentation/free/geosparql-support.html)
- a free version

<img src="graphdb_logo.png" alt="GraphDB">

### 2.1 Installation of GraphDB. <a name="graphdb"></a>

- **Step 1.** Go to the [page of GraphDB](https://www.ontotext.com/products/graphdb/) to get a free copy of the software.
- **Step 2.** Fill the form and request a link to your copy of the software. You should receive a email with download links. 
- **Step 3.** Download and install a desktop version of the software for your platform (see [quick start quid](http://graphdb.ontotext.com/documentation/8.9/free/quick-start-guide.html#run-graphdb-as-a-desktop-installation)).   
- **Step 4.** Run GraphDB. The Web interface of the triple store is available at [http://localhost:7200/](http://localhost:7200/).

### 2.2 Test the installation <a name="test"></a>

- **Step 5.** Create a test repository. [See instructions on how to...](http://graphdb.ontotext.com/documentation/8.9/free/quick-start-guide.html#create-a-repository).
- **Step 6.** Query the created repository. GraphDB automatically loads core vocabularies to 
a new repository. These can be queried. Therefore, select the created repository from the 
 drop down menu, and click the SPARQL menu tab. Run the default query that returns 
 the first 100 triples from the repository:
 
 ```` sparql
 select * 
 where {
      	?s ?p ?o .
     } limit 100      
````

The query results will be rendered as a table. 

### 2.3 Allow requests from other domains <a name="cors"></a>

- **Step 7.** Learn the endpoint address of your GraphDB. Go to *Setup* -> *Repositories* 
and *copy repository URL to clipboard*. See the figure:

  <img src="graphdb_endpoint_url.png" alt="copy repository URL to clipboard">
  
  In GraphDB, the generic schema for the repository URL looks 
  like:

  ```
  http://{ip_address}:{port}/repositories/{repository_ID}
  ```
  
  Such a repository URL can be used to query local data from external Web pages via SPARQL protocol
  which makes it a part of the Web of Data.  
  
- **Step 8.** 




<img src="graphdb_logfile.png" alt="GraphDB console">


## 3. Frontend <a name="frontend"></a>

### 3.1 YASGUI: Yet Another Sparql GUI <a name="yasgui"></a>

<img src="yasgui.png" alt="YasGui">
Can be accessed on yasgui.org.
Can be integrated into a wab page like this:

### 3.2 Sparklis <a name="sparklis"></a>
# Introduction
Tutorials and assignments of this course require installation of some tools to mimic a common architecture of 
Linked Data applications. 

# Tools

## Backend: Triplesore.
Databases built for the storage and retrieval of triples using semantic queries are called triplestores. 
The list of existing implementation is quite impressive and includes about 50 different solutions. 
For tutorial we will install and use **[GraphDB](https://www.ontotext.com/products/graphdb/)**, 
developed by [Ontotext](https://www.ontotext.com/), because it has: 
- a lovely Graphical User Interface
- a support of [geoSPARQL](http://graphdb.ontotext.com/documentation/free/geosparql-support.html)
- a free version

<img src="graphdb_logo.png" alt="GraphDB">

### Installation of GraphDB.

- **Step 1.** Go to the [page of GraphDB](https://www.ontotext.com/products/graphdb/) to get a free copy of the software.
- **Step 2.** Fill the form and request a link to your copy of the software. You should receive a email with download links. 
- **Step 3.** Download and install a desktop version of the software for your platform (see [quick start quid](http://graphdb.ontotext.com/documentation/8.9/free/quick-start-guide.html#run-graphdb-as-a-desktop-installation)).   
- **Step 4.** Run GraphDB. The Web interface of the triple store is available at [http://localhost:7200/](http://localhost:7200/).

### Test the installation

- **Step 5.** Create a test repository. [See instructions on how to...](http://graphdb.ontotext.com/documentation/8.9/free/quick-start-guide.html#create-a-repository).
- **Step 6.** Learn the endpoint address of GraphDB. Go to *Setup* -> *Repositories* 
and *copy repository URL to clipboard*. The URL address of the repositories endpoint will look like:
    - `http://{ip address}:7200/repositories/{repositoryID}` 
    - `http://localhost:7200/repositories/{repositoryID}` 

<img src="graphdb_endpoint_url.png" alt="copy repository URL to clipboard">

### Allow requests from other domains


<img src="graphdb_logfile.png" alt="GraphDB console">


# Frontend: 

## YASGUI: Yet Another Sparql GUI

<img src="yasgui.png" alt="YasGui">
Can be accessed on yasgui.org.
Can be integrated into a wab page like this:

## Sparklis
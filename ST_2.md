---
layout: page
title:  "Assignment Day 2: Query RDF data"
subtitle: "Start talk in SPARQL"
---

<link href='https://cdn.jsdelivr.net/npm/yasgui@2.7.29/dist/yasgui.min.css' rel='stylesheet' type='text/css'/>
<script src='https://cdn.jsdelivr.net/npm/yasgui@2.7.29/dist/yasgui.min.js'></script>

In this tutorial you will learn how to query Linked Data. 
[SPARQL](https://www.PAw3.org/TR/sparql11-query/) is the query language for the Semantic Web and Linked Data.
SPARQL is very expressive and capable of federated querying. The former allows constructing complex queries 
when the latter gives possibility to query more than one repository on runtime.
As a consequence, it is dead easy to make a query that crashes any repository. 
Therefore, make sure that your queries don't multiply everything by everything.

---------------

## Content
---
- [Prerequisite: Load the Data](#ltb)
  - [Step 1. Download the content of a study area as RDF](#step1)
  - [Step 2. Change file extension](#step2)
  - [Step 3. Create a new repository](#step3)
  - [Step 4. Upload the data into the repository](#step4)
- [Query interface](#yasgui)
- [Some query examples](#examples)

--------------

## Prerequisite: Load the Data   <a name="#ltb"></a>

Before we can start the tutorial we need to obtain the data and to upload it into the triplestore.  
We will use data from the LivingTextbook, namely data from your study areas. 
Therefore, the first step is to download an RDF-version of your study area data. 

- **Step 1.** Download the content of a study area as RDF. <a name="#step1"></a>
Go to the dashboard of your study area and click ***Data*** -> ***Export*** . After that, on the download page you 
will be able to specify the required ***Export type*** as ***RDF (JSON-LD)*** . [JSON-LD](https://json-ld.org/) is 
one of the formats used for serialising RDF data. Other example formats 
are [RDF/XML](https://www.w3.org/TR/rdf-syntax-grammar/), [Turtle](https://www.w3.org/TR/turtle/), 
[N-triples](https://www.w3.org/TR/n-triples/) etc. Click the ***Export*** button to start downloading. 

- **Step 2.** Change file extension. <a name="#step2"></a>
The downloaded file has **.json** extension. Before it can be loaded into GraphDB, the extension
 needs to be changed to **.jsonld** . Rename the file, so it is **.jsonld** .
 
- **Step 3.** Create a new repository.  <a name="#step3"></a>
Create a new repository with repository ID *ltb*. [See instructions on how to...](http://graphdb.ontotext.com/documentation/8.9/free/quick-start-guide.html#create-a-repository).

- **Step 4.** Upload the data into the repository. <a name="#step4"></a> 
Make sure that *"ltb"* is your active repository. Then click ***Import*** -> ***RDF***. 
Chose ***Upload rdf Files***  and provide the path to the your JSON-LD file that has extension **.jsonld**
 
## Query interface <a name="#yasgui"></a>

For this tutorial we will use the [YasGUI: Yet Another SPARQL Graphical User Interface](http://yasgui.org/). 
It has quite common appearance for such interfaces. 
From the figure below you can see that it consists of four main elements as follows:
1. endpoint selector
2. query form
3. query result set
4.  buttons to control the visualisation of the query results. 

The ***Run*** button executes the query given in the ***Query form*** against the SPARQL endpoint specified 
in the ***Endpoint selector***. The results of the query are rendered in the ***Query result set***
 using visualisation technique from a number of ***visualisation options***. 

![YasGUI Query interface](yasgui_anat_red.png)

<div style="color: #31708f; background-color: #d9edf7; border-color: #bce8f1; padding: 15px; margin-bottom: 20px; border: 1px solid transparent; border-radius: 4px;">
  <h2 style="color: #31708f;">Important</h2>
  <p>Make sure that you use a correct endpoint address in the Endpoint Selector </p>
</div>

By default the query form contains the following query which retrieves 10 triples from an endpoint:

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT * 
WHERE {
  ?sub ?pred ?obj .
} 
LIMIT 10

```

<div style="color: #31708f; background-color: #d9edf7; border-color: #bce8f1; padding: 15px; margin-bottom: 20px; border: 1px solid transparent; border-radius: 4px;">
  <h2 style="color: #31708f;">Important</h2>
  <p>Even though most of the repositories set limitations on query runtime and the number
     of output triples to protect the service, it is a good practice to use <strong>LIMIT</strong> 
     keyword in your queries to limit number of triples that triple store returns.
     Using <strong>LIMIT</strong> will increase your performance of query development because you
     will not waste time waiting while a triplestore sends back millions of triples that you don't
     need for development. </p>
</div>

## Basic SPARQL query  <a name="#sparql"></a>

It is advised to read [SPARQL documentation](https://www.w3.org/TR/sparql11-query/) to get good understanding of the query language.
Here we give very basic explanation and examples.

> Most forms of SPARQL query contain a set of triple patterns called a basic graph pattern.
Triple patterns are like RDF triples except that each of the subject, predicate and object
may be a variable.

In the default query a basic graph pattern is expressed as three variables  `?sub ?pred ?obj` .

```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT * 
WHERE {
  ?sub ?pred ?obj .
} 
LIMIT 10

```

The first variable `?sub` represents the subject of a triple, `?pred` is for the predicate and `?obj` for the object.
Such a triple pattern is valid for every triple in a triple store, therefore the result of the
query will be 10 first triples since the **LIMIT** is set to 10. 

Each of the variables in a triple pattern can be substitute with an RDF term.

## Useful information: classes and labels <a name="#class&label"></a>

[The third rule of linked data](https://www.w3.org/DesignIssues/LinkedData.html) stays:
3. When someone looks up a URI, provide useful information, using the standards
([RDF](https://www.w3.org/RDF/) and [SPARQL](https://www.w3.org/TR/rdf-sparql-query/))

The RDF standard defines a data model (as subject-predicate-object triples) and a basic vocabulary 
that allows describing both Web documents and concepts from the real world—people, organisations, 
topics, things—in a computer-processable way.
In other words, things named with URIs can be described using this basic vocabulary. 
A basic description always include information that answers two questions *"what is it"* and *"how is it called"*.

### What is it: a class <a name="#class"></a>

For example, consider a statement: "*Berlin is a city*" . 
RDF provides a formal way to describe this:

```ntriples
<http://dbpedia.org/resource/Berlin> <http://www.w3.org/1999/02/22-rdf-syntax-ns#type> <http://dbpedia.org/ontology/City> .
```

This RDF statement (triple) literally says: "Berlin is a city"

The triple in the snippet above consists of three URIs - URI for Berlin, 
URI for relation (type) and URI representing the concept of a city. 
As mentioned above URIs can be used to describe abstract concepts (e.g a city) 
apart from real-life objects (e.g real people).
The collection of such concepts are called vocabularies or ontologies.
People are encouraged to (re)use existing ontologies or to make their own. 

<div style="color: #31708f; background-color: #d9edf7; border-color: #bce8f1; padding: 15px; margin-bottom: 20px; border: 1px solid transparent; border-radius: 4px;">
  <h2 style="color: #31708f;">Important</h2>
  <p>URIs do not provide meaningful information by themselves. 
     The URI of <i><http://dbpedia.org/resource/Berlin></i>
     does not say anything about what it is. 
     Only information related to this URI describes the city of Berlin.
     Most useful information is about the type of a thing and its label. </p>
</div>

Therefore, one of the most useful relations in the world of RDF is 
`<http://www.w3.org/1999/02/22-rdf-syntax-ns#type>` because it is used to state that a subject 
of a triple belongs to a certain class of things expressed as an object. 

### First 10 of a class

Therefore, let's retrieve any 10 concepts from your data. In the LivingTextbook, concepts are classified 
using `	http://www.w3.org/2004/02/skos/core#Concept, a [term](https://www.w3.org/2009/08/skos-reference/skos.html#Concept) defined by 
the [Simple Knowledge Organization System(SKOS)](https://www.w3.org/2004/02/skos/) ontology. This is a very common 
ontology for structuring concepts.  

To retrieve any 10 concepts from the repository  we just need to make a triple pattern where 
subject is unknown (a variable), a predicate is `<http://www.w3.org/1999/02/22-rdf-syntax-ns#type>`  
and an object is the class `<http://www.w3.org/2004/02/skos/core#Concept>`.

<div style="color: #31708f; background-color: #d9edf7; border-color: #bce8f1; padding: 15px; margin-bottom: 20px; border: 1px solid transparent; border-radius: 4px;">
  <h2 style="color: #31708f;">Important</h2>
  <p>The keyword <i><strong>"a"</strong></i> can be used as a predicate in a triple 
  pattern and is an alternative for the IRI  <http://www.w3.org/1999/02/22-rdf-syntax-ns#type>. 
  This keyword is case-sensitive. 
  </p>
</div>

Therefore the query will be:

```SPARQL
SELECT ?sub 
WHERE {
  ?sub <http://www.w3.org/1999/02/22-rdf-syntax-ns#type> <http://www.w3.org/2004/02/skos/core#Concept>.
}

Limit 10
```

Copy this query and run it in YasGUI. 
SPARQL allows shortenning queries to improve clarity and readability .  
The same query can be written as follows:

```SPARQL
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>

SELECT ?sub 
WHERE {
  ?sub a skos:Concept .
}
LIMIT 10
```
In the query, a namespace prefix binding (skos) as well as keyword **a** are used to shorten 
the declaration of the pattern. Copy and run the shorten query to see that it
retrieves results identical to the long one. 

### And their names

One can notice that since URIs do not provide useful information by themselves
 there is not much value in the list of URIs that we retrieved in the previous section. 
Therefore, let's ask about the labels of those concepts we found before. 
There is a dedicated RDF relation that helps to link subjects to literal values representing
names of things `<http://www.w3.org/2000/01/rdf-schema#label>` .

We need to ad 1 additional triple pattern where the subject is the same as 
in the first triple pattern (same variable `?sub`); predicate is 
`<http://www.w3.org/2000/01/rdf-schema#label>` and object is a new variable `?label`.  

```SPARQL
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT ?sub ?label
WHERE {
  ?sub a skos:Concept .
  ?sub rdfs:label ?label .
}
LIMIT 10
```

In the query, we specified a class of a variable (`?sub a skos:Concept .`) 
and we added an additional triple pattern that asks for objects (`?label`) 
that are connected to `?sub` using `rdfs:label` predicate (`?s foaf:name ?name`). 
Run the query in YasGui to see URIs and labels of the first 10 concepts. 

## Federation

The [SPARQL specification](https://www.w3.org/TR/2013/REC-sparql11-federated-query-20130321/) states:

>RDF is a directed, labeled graph data format for representing information in the Web.
>SPARQL can be used to express queries across diverse data sources, whether the data is stored
natively as RDF or viewed as RDF via middleware.
SPARQL allows executing queries distributed over different SPARQL endpoints.
The SERVICE keyword is used to support queries that merge data distributed across the Web.

To put it short, federation makes it possible to query more than one endpoint at a time.
Example below retrieves first 10 triples from DBpedia:

```SPARQL
SELECT ?s ?p ?o
  {
    Service <http://dbpedia.org/sparql>
      {?s ?p ?o}
  }
Limit 10
```

As it was stated above LinkDaLe works with the endpoint <http://viruoso.almere.pilod.nl/sparql>
Therefore, all the queries is executed by that endpoint. The query above was sent
 to <http://virtuso.almere.pilod.nl/sparql> . The endpoint precessed the query (found ***SERVICE*** keyword) and
 sent another query to DBpedia endpoint specified after the ***SERVICE*** keyword. The DBpedia endpoint processed the request returned it to <http://virtuoso.almere.pilod.nl:8890/sparql> and then, it was back in the browser.


---
layout: page
title:  "Assignment: Semantic Integration"
subtitle: "classes and labels"
---

---------------

## Content
---

- [Federation](#fed)
- [Linking with SPARQL](#recon)
  - [Assignment: Semantic Integration](#ass1)
    - [Part A](#partA)
    - [Part B](#partB)

--------------
## Federation <a name="fed"></a>

The [SPARQL specification](https://www.w3.org/TR/2013/REC-sparql11-federated-query-20130321/) states:

>RDF is a directed, labeled graph data format for representing information in the Web.
>SPARQL can be used to express queries across diverse data sources, whether the data is stored
natively as RDF or viewed as RDF via middleware.
SPARQL allows executing queries distributed over different SPARQL endpoints.
The SERVICE keyword is used to support queries that merge data distributed across the Web.

To put it short, federation makes it possible to query more than one endpoint at a time.
For example, consider the query below. It retrieves first 10 triples from DBpedia:

```SPARQL
SELECT ?s ?p ?o
  {
    SERVICE <http://dbpedia.org/sparql>
      {?s ?p ?o}
  }
Limit 10
```

As it was stated above YasGui works with the endpoint specified in the ***Endpoint selector***.
Therefore, all the queries is executed by that endpoint. For this assignment we will use `<http://localhost:7200/repositories/ltb>` .

If you run the query above, it will be sent to `<http://localhost:7200/repositories/ltb>`. 
The endpoint will precess the query (found `SERVICE` keyword ) and will send another query to 
DBpedia endpoint (`<https://dbpedia.org/sparql>`) with the content given after the `SERVICE` keyword. 
The DBpedia endpoint will process the request and will return the results back 
to `<http://localhost:7200/repositories/ltb>` and then, it will be back in the browser.

Try it yourself! Copy the query and Run it. 


## Linking with SPARQL <a name="recon"></a>

In the [step 4 of Tutorial: Create some RDF data](day1_2.md#step4)
you used the interface of OntoRefine to reconcile the names of the cities against Wikidata data. 
Such services rely on matching literal values between resources of a particular type (e.g municipality of 
the Netherlands as in the [Tutorial: Create some RDF data](day1_2.md)).
Same functionality can be achieved with SPARQL.
The query below does exactly the same but with LTB data. 
It tries to match labels of concepts from the LTB data and concepts from DBpedia. 
The query is annotated using `#` which allows providing human-readable comments that are 
invisible for the query processor. 

```SPARQL
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT ?sub ?label ?inDBpedia
{
# Part of the query that retrieves URIs and labels of concepts in LTB data
  
 ?sub a skos:Concept .
 ?sub rdfs:label ?label .
  
# Service part of the query that is executed by a remote endpoint (dbpedia)
  
  Service <http://dbpedia.org/sparql> {
    
# Part of the query that matches concepts from DBpedia 
# (the first triple pattern: "?inDBpedia a skos:Concept ." ) 
# based on the literal values of their labels 
# (the second triple pattern: "?inDBpedia rdfs:label ?label .")
    
    ?inDBpedia a skos:Concept .
    ?inDBpedia rdfs:label ?label .
    
  }
}
# notice a limit
LIMIT 1000
```

Copy the query and run it with YasGui. 


### Assignment: Semantic Integration <a name="ass1"></a>

Change the query below in such a way that it provides the greatest number of results with the 
most accurate semantic matching. In other words, you are asked to find such a combination of class declarations (can be more than one)
in line 9 (the commented out line) that would yield the greatest number of semantically accurate results. 
 
```SPARQL
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT ?sub ?label ?dbcon
{
 ?sub a skos:Concept .
  ?sub rdfs:label ?label .
  Service <http://dbpedia.org/sparql> {
#   ?dbcon a skos:Concept .
    ?dbcon rdfs:label ?label .
  }
}
LIMIT 1000
```

- Part A.  <a name="partA"></a> Choose 5 concepts from DBpedia that in your opinion have the best match. 
Add them to your LTB study area (create) and link them to matching concepts using relation "same as". 
To denote that those concepts belong to DBpedia put `DBpedia:` before their names and 
copy the concept URL into the "External resources" field in LTB.

- Part B.  <a name="partB"></a> Add concepts that represent DBpedia classes used in the query. 
Link them to the 5 DBpedia concepts created in Part A using "is a kind of" relation. 
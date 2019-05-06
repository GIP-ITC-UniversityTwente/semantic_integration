---
layout: page
title:  "Assignment Day 1: Query Linked Data"
subtitle: "Moving from the 3rd star"
---

In this tutorial you will learn how to query Linked Data you have created.
[SPARQL](https://www.PAw3.org/TR/sparql11-query/) is the query language for the Semantic Web and Linked Data.
SPARQL is very expressive and capable of federated querying. The former allows constructing complex queries when
the latter gives possibility to query more than one repository on runtime.
As a consequence, it is dead easy to make a query that crashes any repository. 
Therefore, make sure that your queries don't multiply everything by everything.

---------------

## Content
---
- [1. Use Limit](#limit)
- [2. Step 1](#step1)

--------------

## Use LIMIT  <a name="limit"></a>

However, even though most of the repositories set limitations on query runtime and the number
of output triples to protect the service, it is a good practice to use ***LIMIT*** keyword in your queries to limit number of triples that triple store returns.
Using ***LIMIT*** will increase your performance of query development because you
will not waste time waiting while a triplestore sends back millions of triples that you don't
need for development.

For example, the default query with a limit set to 100 will retrieve only first 100 solutions:

```SPARQL
SELECT ?s ?p ?o
{?s ?p ?o}
Limit 100

```

---
layout: page
title:  "Assignment: Geospatial Linked Data"
subtitle: "Report part 1 & 2"
---



---------------

## Content
---

- [Ontologies](#onto)
  - [Report part 1: You will LOV it!](#lov)
- [Sources of Linked Data](#sources)
  - [Report part 2: a-LOD of Geo Data](#lodv)

--------------


## Ontologies <a name="onto"></a>

The first attempt to create a geo extension to RDF was made in 2003, 
when the W3C Semantic Web Interest Group issued the Basic Geo Vocabulary 
which provided means to represent 
WGS 84 points in RDF. This work was further extended, and in 2007, the W3C 
Geospatial Incubator Group released the GeoOWL 
ontology, which supported the description of points, lines, rectangles, 
and polygon geometries and their associated features. However, this ontology 
also supported only WGS 84 reference system.

The aforementioned ontologies allow representation of 
geographical data in RDF. Nevertheless, in order to enable spatial 
reasoning in querying of RDF data, there is a need to include the 
support of spatial relationships in query language and spatial indexing in  
triple stores. 

>The release of the GeoSPARQL standard by OGC in 2012 became a breakthrough achievement that 
brought qualitative and quantitative spatial reasoning to the Web of Data. 
This effort used a combination of well-understood and widely used OGC standards such as Geography Markup Language (GML) 
and well-known text (WKT) literals for representation of geospatial data. The OGC’s Simple Features, 
Egenhofer’s 9-intersection model, and RCC8 were used as topological relationship vocabularies and ontologies 
for qualitative reasoning. 

### Report part 1: You will LOV it! <a name="lov"></a>

Find as many geospatial ontologies as you can (min 5) 
using the [Linked Open Vocabulary](https://lov.linkeddata.es/dataset/lov) 
service. Fill the table as follows and save it as "Examples" of ontologies in your LTB model 
(if you don't have the "ontology" concept in your LTB, create it first then) :

| Ontology name | Preferable prefix | Base URL | Short description |
| ---- | --- | ------ | ------------------ |
| GeoSPARQL | gsp: | http://www.opengis.net/ont/geosparql# | The OGC GeoSPARQL standard supports representing and querying geospatial data on the Semantic Web |
| WGS84 Geo Positioning | geo | http://www.w3.org/2003/01/geo/wgs84_pos# | Basic Geo (WGS84 lat/long) Vocabulary. This is a basic RDF vocabulary that provides the Semantic Web community with a namespace for representing lat(itude), long(itude) and other information about spatially-located things, using WGS84 as a reference datum. |
| ... | ... | ... | ... |

You will get 2 points for this part of the report. 

## Sources of Linked Data <a name="sources"></a>

Linked Data initiatives promote the adoption of semantic formats. 
This has enabled users to publish structured data online creating a 
global data space. In this context, several collaborative projects have 
emerged, resulting in a growing number of freely available knowledge bases. 
The W3C SWEO Linking Open Data community project is aimed at publishing 
various open data sets as RDF and setting RDF links between data items from 
different data sources. So far, the project has published 570 data sets that 
are connected by 2909 link sets. Together these resources form the so-called 
the Linked Open Data cloud, a collection of data sets published under 
Creative Commons or Talis licenses. 
The size of the cloud is large; it contains more than 30 billion triples, 
which makes it an outstanding source of knowledge.

### Report part 2: a-LOD of Geo Data <a name="sources"></a>

Analyse the content of [Linked Open Data Cloud](https://lod-cloud.net/) and 
 fill the table describing the 5 largest geospatial datasets. Save the results 
 as "Examples" of Linked Open Data in your LTB model 
 (if you don't have the "LOD" concept in your LTB, create it first then) :

| Dataset name | SPARQL endpoint address | Short description |
| ---- | --- | -------------- |
| DBpedia | <http://dbpedia.org/sparql> | DBpedia.org is a community effort to extract structured information from Wikipedia and to make this information available on the Web.  |
| ... | ... | ... |

You will get 2 points for this part of the report. 
---
layout: page
title:  "Assignment Day 3: Data Story"
subtitle: "Report part 3"
---

In this tutorial you will build you own data story. 
Since Linked Data is a relatively new technology for most users, many of them are
unaware of the potential that can be unlocked. To bridge the gap between (a) the
vast but implicit potential that a Linked Dataset encapsulates, and (b) the specific
and often more explicit use cases a prototypical user may have in mind. The concept
of Data Stories was introduced and developed by 
[Folmer and Beek (2017)](https://scholarworks.umass.edu/foss4g/vol17/iss1/23/). 

---------------

## Content
---
- [Data Stories](#story)
- [Report part 3: Where you from?](#where)

--------------

## Data Stories.  <a name="story"></a>
A Data Story allows a specific use case to be explained to a potential user through a
sequence of data examples, that are connected by an overarching story. To be as
generic as possible, the data examples that compose a Data Story are
visualizations of SPARQL result sets. This ensures that the components of a Data
Story are declarative (how the data is obtained is encoded in the SPARQL query),
reproducible (the query is recomputed when the Data Story is generated), and
modifiable (advanced users can click a button to open the SPARQL query view,
where the query can be altered and rerun). 

### Report part 3: Where are you from?  <a name="where"></a>


- First, create a concept dedicated to a data story in LTB. You will create a report 
using this concept.

- Second, using YasGUI together with DBpedia data create a map that would show
 the location of your home town.
 
To create such a map, you will need to access location information 
(coordinates) based on the spelling of the name of your home town.
Explain steps taken to create the query in the field `"How to"` of LTB. 
Provide a shareable link to the query (use the share button in YasGUI) 
and the screen capture with the map.
You will be graded as follows: 

Deliverables: 

| Condition | Value (points) |
|: ---- |: --- :|
| Shareable link from YasGUI | 0.25 |
| Screen capture with the map | 0.25 |
| Explanation of steps taken | 0.5  |
| Query consists of no more than 2 triple patterns | 0.5 |
| Use of native language in the hometown name| 0.5 | 

<div style="color: #31708f; background-color: #d9edf7; border-color: #bce8f1; padding: 15px; margin-bottom: 20px; border: 1px solid transparent; border-radius: 4px;">
  <h2 style="color: #31708f;">Important</h2>
  <p>YasGUI nativally accepts geographical coordinates 
  in the WKT serialisation. Therefore, make sure that you use 
  geometry that looks like: <strong><i>POINT(long lat)</i></strong>
  </p>
</div>



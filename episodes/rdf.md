---
title: "Resource Description Framework (RDF)"
teaching: 20
exercises: 10
---

::: questions 

- What is the Resource Description Framework (RDF)?
- How can information be linked using triples and URI?  
:::

::: objectives
After completing this episode, participants should be able to

- describe the basics of the Resource Description Framework (RDF),
- name the elements of a triple,
- find URI for RDF triple elements and create RDF statements. 
:::


RDF was originally conceived by the World Wide Web Consortium (W3C) as a standard for describing metadata. 
It is now considered a fundamental building block of the Semantic Web and is similar to the classical methods 
for modeling concepts, such as the Entity-Relationship Model mentioned in the introduction.

Data in RDF are statements about resources. These statements are modeled as triples. The set of triples forms a 
(mathematical) graph and is called an RDF model. 

```xml
<subject/><predicate/><object/>
<artist>Frida Kahlo></artist><creator>is creator of</creator><artwork>The two fridas</artwork>
```

The subject and predicate are always resources. This means that they are entities with an extended set of information. The object can be either a resource or a literal. Literals are strings that can be interpreted using a specified data type like boolean values, numbers, or dates. Unique identifiers (e.g. URI) are used to identify resources.  

A Uniform Resource Identifier (URI) is an identifier consisting of a string of characters used to identify an abstract or physical resource. They are built in a similar way as a web address (URL). The aforementioned GND or Wikidata IDs are examples. Different sources can be linked together using the URI. Remember the graphic in the introduction. 

The predicate is also defined by a URI. This is possible, for example, when the relationship is defined by a metadata 
standard. The metadata fields of the standards have their own URI. The relationship between an artist and her artwork can be 
modeled using the Dublin Core element "creator". 
```
<https://www.wikidata.org/wiki/Q5588><http://purl.org/dc/terms/creator><https://www.wikidata.org/wiki/Q3232010>
```
This example means exactly the same as the previous example: Frida Kahlo is creator of "The two Fridas" by using the identifier of Wikidata and Dublin Core. 

Technically, RDF can be implemented in several formats, including JSON-LD and RDF/XML - two special formats of JSON and XML for RDF.


::: challenge

### Exercise

Take a closer look at the [Wikidata resource of Frida Kahlos painting "The two Fridas"](https://www.wikidata.org/wiki/Q3232010). Can you find an alternative way of describing the predicate instead of using Dublin Core?

::: solution

### Solution

[creator property](https://www.wikidata.org/wiki/Property:P170):  
The information listed in Wikidata for an entity is all labeled with properties such as location, genre, creator etc. These properties themselves have an identifier and are therefore standardized. All paintings can be modeled in a consistent way. The creator property can be used similiar to the Dublin Core element of creator. 
:::
:::

::: challenge

### Exercise

Use wikidata to create a triple for the following statements:  
1) Michelangelo is the creator of the Pietà.  
2) Michelangelo was born in Caprese Michelangelo.  
3) The Pietà is located in the St. Peter's Basilica.   

::: solution

### Solution

```
<https://www.wikidata.org/wiki/Q5592><https://www.wikidata.org/wiki/Property:P170><https://www.wikidata.org/wiki/Q235242>
<https://www.wikidata.org/wiki/Q5592><https://www.wikidata.org/wiki/Property:P19><https://www.wikidata.org/wiki/Q52069>
<https://www.wikidata.org/wiki/Q235242><https://www.wikidata.org/wiki/Property:P276h><ttps://www.wikidata.org/wiki/Q12512>
```
:::
:::
   


::: keypoints
- RDF is a standard model for data interchange on the Web.  
- Statements are modeled as triples. Using URI, these triples link data (and thus all the information behind it) and form a (mathematical) graph.
:::

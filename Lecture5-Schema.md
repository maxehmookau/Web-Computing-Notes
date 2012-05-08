Lecture 5 - Schema
==

DTDs are lacking. Developers weren't all that impressed.

>The main concern is that DTDs are written using their own peculiar syntax and cannot be processed in generic ways.

So why not use XML to describe XML? That's where `schemas` come in!

Why do DTDs suck?
--

* No constraints on character data. `#PCDATA` just allows any text to be input. This may not always be appropriate. 
* No support for `namespaces`. 
* Not very `modular` and too `low-level`.
* Difficult, repetitive and hard to maintain due to lack of object-orientated structure.
* No `white-space` control.
* No embedded self-documentation, except `<!-- comments -->` which aren't really sufficient. 
* No default values for elements.

>The plan for schemas was to improve on as many of these points as possible.

Schema Flavours
--
Schema comes in a few different types. We focus on `W3C Schema`. *Just because*. 

>An XML Schema document is an XML document marked up using the XML Schema markup language.

The XML preamble specifies this as follows:
 
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema">
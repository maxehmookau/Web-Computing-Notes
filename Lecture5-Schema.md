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


Writing Schema
--
>An XML Schema document is an XML document marked up using the XML Schema markup language.

The XML preamble specifies this as follows:
 
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema">

An XML schema document is a list of declarations much like a DTD, but formatted more like XML. They are made up of `elements`, `types` and `attributes`.

###Elements

Each element needs to be declared as such. **(Note the `xsd` namespace)**

    <xsd:element name="foo" type="bar" />

Where name is the name of the element and type is any primitive type. These are all defined somewhere.

Occurance constraints also work in schema like DTDs. Each element has the attributed `minOccurs` and `maxOccurs`.

    <xsd:element name="cheese" type="string" minOccurs="0" maxOccurs="2" />

Also like DTDs, we can define `composite elements`. The DTD:

    <!ELEMENT payment (amount , cheque_number | visa_number) >

Is written as follows in schema:

    <xsd:sequence>
      <xsd:element name="amount" type="integer"/>
      <xsd:choice>
        <xsd:element name="cheque_number" type="integer"/>
        <xsd:element name="visa_number" type="integer"/>
      </xsd:choice>
    </xsd:sequence>

We can also specify `type` to be a more complex type, itself made up of `elements` and `attributes`, by using the `xsd:complexType` namespace.

    <xsd:complexType name="record">
       <xsd:sequence>
         <xsd:element name="cname" type="xsd:string"/>
         <xsd:element name="email" type="xsd:string"/>
       </xsd:sequence>
    </xsd:complexType>
    <xsd:element name="owner" type="record"/> 

Where the schema defines an XML document of `owners` which are of type `record` where `record` is defined as a complex type. 
Lecture 2 - XML: eXtensible Markup Language
====
XML is not a markup language in the same sense as HTML. It is a framework for defining markup languages using the same tools. The collection of tags is not fixed. You define the tags to match the data being defined. 
The commonality between XML markup is the way in which the metadata is presented. 

There are common libraries and tools for processing XML documents. 

XML is designed to `separate syntax from semantics` by structuring data with tags. Stylesheets then use the structure to provide the semantics. This encourages `internationalisation and platform independence. `

It is however not designed to replace HTML as XML on its own cannot process text. 

Whereas defining a recipe in HTML would require us to create the layout in a markup language and add the data, XML allows us to define a datatype. 

    <recipe>

      <title>Rhubarb Cobbler</title>
      <author><email>Maggie.Herrick@bbs.mhv.net</email></author>
      <date>Wed, 14 Jun 95</date>

      <description>
        Rhubarb Cobbler made with bananas as the main sweetener. It was delicious.     Basically it was
      </description>

    <ingredients>
      <item>
        <amount>2 1/2 cups</amount>
        <type>diced rhubarb</type>
      </item>
      <item>
        <amount>2 tablespoons</amount>
        <type>sugar</type>
      </item>
      <item>
        <amount>2</amount>
        <type>fairly ripe bananas</type>
      </item>
      <item>
        <amount>1/4 teaspoon</amount>
        <type>cinnamon</type>
      </item>
      <item>
        <amount>dash of</amount>
        <type>nutmeg</type>
      </item>
    </ingredients>
  
    <preparation>
      Combine all and use as cobbler, pie, or crisp.
    </preparation>
  
    <related url="#GardenQuiche">Garden Quiche</related>

  This illustrates that the markup tags are used for logical structure. However, to render it, we need a `stylesheet` to define presentation semantics. 


XML and Databases
--
Whether we use XML or a database to define data types is dependent on the `intended use` of the data. Sometimes features such as `size` can stop XML being the most efficient form of data manipulation.

Conceptual View of XML
--
An XML document is an `ordered` and `labelled` tree. 

`Leaf nodes` contain data, usually strings.

`Element nodes` are made of a tag (or type) and a set of attributes. 

Example of XML
--
    <?xml version = "1.0"?>
    <!-- that was a processing instruction -->
    <!-- and these lines are comments -->
    
    <myFirstTag>
    
       Some character data
    
       <childElement attribute-name="this is an attribute value">
          Some more character data
       </childElement>
    
       <anEmptyElement></anEmptyElement>
    
       <anotherEmptyElement/>
    
    </myFirstTag>

Tags always begin 

    <tag_name>

and end

    </tag_name>

with empty elements defined as such:

    <tag_name/>

Defining XML
---

CDATA - Not parsed by XML readers.
    
    <![CDATA[Skipped by the parser]]
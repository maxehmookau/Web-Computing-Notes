Lecture 7 - XSLT
=======

>One of the intended uses of XML is that a single data file stored in an XML format can be used for varied applications. In fact, even for just viewing the file in a browser, a single file could be rendered in multiple ways by using a CSS stylesheet.

Unfortunately, CSS has some fairly `serious limitations` when it comes to data manipulation.

* Data cannot be modified or restructured using CSS.
* Data cannot be deleted (only hidden) using CSS.

Neither of these things are particularly unusual data manipulation operations, but CSS cannot handle them. We need some form of stylesheet transformation. So that the CSS can perform some manipulation operations. This is where `XSLT` comes in. XSLT is more complex than just another form of styling though, in fact it doesn't completely remove the need for semantic styling using CSS.

>XSLT transforms essentially map XML documents according to some DTD/Schema to XML documents according to another DTD/Schema.

Writing XSLT
--
An XSLT document is just an XML document. *What a surprise.* Just make sure to use the XSLT namespace as defined by W3C.

    <?xml version="1.0"?>
    <xsl:stylesheet version="1.0" 
         xmlns:xsl="http://www.w3.org/1999/XSL/Transform" >
       ...
    </xsl:stylesheet>

Using XPATH
--
XPATH allows us to treat XML files like structured, `labelled trees`. Programs that use XPATH navigate this tree. 

>At all times, there is node which is considered to be the 'current' node, i.e. the place in the tree where processing is currently taking place. We refer to this as the context node.

XPATH is supercool and allows us to search an XML document quickly using its syntax.

* foo - selects all child elements of the context node called <foo> elements

* @bar - selects all attributes of the context node called bar
* \* - selects all child elements of the context node
* \* - selects all attributes of the context node
* text() - selects only the text nodes which are children of the context node
* node() - selects all child nodes, irrespective of type
* // - selects all descendants of the context node
* . - selects the context node itself
* .. - selects the parent of the context node


So something like 

    /story/chapter[1]/text()

would return the text in chapter 1.

Predicates in XPATH
--
XPATH allows more detailed searching using predicates.

    book/title[@subtitle='Or what you will']

Does pretty much what you'd expect it to.
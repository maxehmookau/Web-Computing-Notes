Lecture 6 - Document Object Model (DOM)
=======

>The Document Object Model (DOM) is an application programming interface (API) for well-formed XML documents.

Using `DOM`, programmers can create, modify, add or delete objects and elements. It is this that effectively transforms XML from plain text to `navigable, hierarchical data structure`. 

>It is an API based on object-oriented design. That is to say, XML documents and their logical structure are modelled using a structured series of objects.

Each node in the XML tree is represented as an object.

Implementing a DOM
--
DOM specifies interfaces rather than specific implementation details which leaves it to be `language-independent`. 

>Therefore DOM applications may provide additional interfaces beyond the DOM and still be DOM compliant.

JAXP
--

JAXP or `Java API for XML Processing` is a DOM compliant implementation of the DOM for Java. It is used as follows:

    import org.w3c.dom.*

This imports the DOM components but no file reading libraries, we'll need these too.


Writing something Using JAXP
--
Firstly, we need a bunch of libraries:

    import javax.xml.parsers.DocumentBuilder;
    import javax.xml.parsers.DocumentBuilderFactory; 
    import javax.xml.parsers.FactoryConfigurationError; 
    import javax.xml.parsers.ParserConfigurationException;
    import org.xml.sax.SAXException; 
    import org.xml.sax.SAXParseException; 
    import java.io.File;
    import java.io.IOException;
    import org.w3c.dom.*;


Then we import and parse an XML file:

    public static void main(String[] args) 
    {
	    areaCode ac = new areaCode();
        ac.readDoc();
        ac.processDoc();
        ac.writeDoc();
    }
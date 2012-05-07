Lecture 4 - Document Type Definitions
==

`Document Type Definitions` or `DTDs` define a particular type of XML document. Because it is extensible and can define any data type, `the definition itself needs defining.` This is where DTDs come in.

DTD Syntax
--
    <!ELEMENT name content>

Where content is the name of a `type`, `#PCDATA` or `EMPTY`.

    <!ELEMENT StudentList (student) > 
    <!ELEMENT student (username, reg_no, name) > 
    <!ELEMENT name (forename, surname) > 
    <!ELEMENT username (#PCDATA) > 
    <!ELEMENT reg_no (#PCDATA) > 
    <!ELEMENT forename (#PCDATA) > 
    <!ELEMENT surname (#PCDATA) > 

The above DTD describes an XML document which describes a `StudentList.`
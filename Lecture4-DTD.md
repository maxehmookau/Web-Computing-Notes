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

The above DTD describes an XML document which describes a `StudentList`.
The root element `StudentList` contains a child node `student` which contains a three child nodes `username`, `reg_no` and `name`. The `username` element contains some character data.

We can use `regular expression` style syntax to further define XML documents. 

    <!ELEMENT name (forename, middlename? surname) >

The definition above for a node called `name` says that a `name` contains exactly one forename, one surname and zero or more middle names. 

    <!ELEMENT email ( header, (#PCDATA | attachment)+ )

This one says that all emails must contain a header and at least one of either character data or an attachment. 

An Example
--

DTD for a `book`
    
    <!DOCTYPE BOOK [
        <!ELEMENT p (#PCDATA)>
        <!ELEMENT BOOK         (OPENER,SUBTITLE?,INTRO?,(SECTION | PART)+)>
        <!ELEMENT OPENER       (TITLE_TEXT)*>
        <!ELEMENT TITLE_TEXT   (#PCDATA)>
        <!ELEMENT SUBTITLE     (#PCDATA)>
        <!ELEMENT INTRO        (HEADER, p+)+>
        <!ELEMENT PART         (HEADER, CHAPTER+)>
        <!ELEMENT SECTION      (HEADER, p+)>
        <!ELEMENT HEADER       (#PCDATA)>
        <!ELEMENT CHAPTER      (CHAPTER_NUM, CHAPTER_TEXT)>
        <!ELEMENT CHAPTER_NUM  (#PCDATA)>
        <!ELEMENT CHAPTER_TEXT (p)+>
    ]>
-
XML file that conforms to the above `DTD`.

    <?xml version="1.0"?>
    <BOOK>
        <OPENER>
            <TITLE_TEXT>All About Me</TITLE_TEXT>
        </OPENER>
        <PART>
            <HEADER>Welcome To My Book</HEADER>
            <CHAPTER>
                <CHAPTER_NUM>CHAPTER 1</CHAPTER_NUM>
                <CHAPTER_TEXT>
                    <p>Glad you want to hear about me.</p>
                    <p>There's so much to say!</p>
                    <p>Where should we start?</p>
                    <p>How about more about me?</p>
                </CHAPTER_TEXT>
            </CHAPTER>
        </PART>
    </BOOK>

External DTDs
--

We can link to external DTDs much like CSS files. They can be `private` or `public`. 

Linking to a private DTD is done as follows:

    <!DOCTYPE name SYSTEM "URI">

Where `URI` is the path to a DTD and `name` is the data type being described. 

A public DTD is defined remotely using the following syntax:

    <!DOCTYPE name PUBLIC "FPI" "URL" >

Where FPI is the `formal public identifier` for the DTD. It is made up of several parts:

* `-` or `+` defines whether it is a standard or non-standard DTD.
* The name of the person responsible for the DTD
* The type of document and version number
* 2 character language code

The fields are separated by `//`. Here's an example:

    <!DOCTYPE BOOK PUBLIC "-//Joseph Smith//General Book Version 5.3//EN" "http://www.library.org/book.dtd">

Attributes in DTDs
--


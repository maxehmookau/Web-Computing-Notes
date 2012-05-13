Lecture 11 - Javascript
=====

Javascript is a `client-side scripting language` for web applications. It is client side as the code is executed within the browser on the client's machine. 

>We don't need to learn Javascript… much.

My First JS
--
    <html>
      <body>
        <script type="text/javascript">
        document.write("Hello World!");
        </script>
      </body>
    </html>

This does as you would expect, writing 'Hello World' to the browser in the `<body>` tag. 

Javascript Functions
--
Like most programming languages, Javascript can define code in parameterised functions. Here's an example of defining and calling a function.

    <html>
      <head>
        <script type="text/javascript">
         function delayedMessage() {
           document.write("<p>I should appear second</p>");
         }
        </script>
      </head>
      <body>
        <script type="text/javascript">
           document.write("<p>I should appear first</p>");
           delayedMessage();
        </script>
      </body>
    </html>

JS Variables
--

Variables are defined:
    
    var name = value;

Types are `very weak` and determined at runtime. 


JS Arrays
---
    coffees = new Array();
    coffees[0] = "One";

etc…

JS Objects
--

    myCar = new.Object();
    myCar.make = "value";
    myCar.colour = "value";

It's *that* easy.

There's plenty of other syntax in JS that's basically identical to every other language. for, while.. etc…

Events in JS
--
This is where it gets cool. Javascript has predefined functions for dealing with certain events in a browser. Things like:

* A mouse click
* A web page or an image loading
* Mouse moving over a hot spot on the web page
* Selecting an input box in an HTML form
* Submitting an HTML form
* A keystroke 

Key Stroke Event
--
    <html>
     <style> ... </style>
     <body>
      <warning onmouseover="alert('GRRRRR');">
         Be Careful, I Bite!
      </warning>
      <p>But, I'm friendly.</p>
     </body>
    </html>

Key Press Event
--

    <script type="text/javascript">
      document.onkeyup = handleKey;
      
    
      function handleKey(e){
         if (e.keyCode == 71) { alert("Thank you very much") ; }
      }
    </script>
gitin10min
==========

Learn Git in 10 minutes.

This one-page guide contains the essential workflow and commands users need to know to get started with Git.

   
Select Language​▼
HOME HTML CSS JAVASCRIPT JQUERY XML ASP.NET PHP SQL MORE... REFERENCES | EXAMPLES | FORUM | ABOUT
JS Tutorial
JS HOME
JS Introduction
JS How To
JS Output
JS Statements
JS Comments
JS Variables
JS Data Types
JS Objects
JS Functions
JS Operators
JS Comparisons
JS Conditions
JS Switch
JS Loop For
JS Loop While
JS Breaks
JS Errors
JS Validation

JS HTML DOM
DOM Intro
DOM HTML
DOM CSS
DOM Events
DOM Nodes

JS Objects
JS Object
JS Number
JS String
JS Date
JS Array
JS Boolean
JS Math
JS RegExp

JS Window
JS Window
JS Screen
JS Location
JS History
JS Navigator
JS PopupAlert
JS Timing
JS Cookies

JS Libraries
JS Libraries
JS jQuery
JS Prototype

JS Examples
JS Examples
JS Objects Examples
JS Browser Examples
JS DOM Examples
JS Quiz
JS Certificate
JS Summary

JS References
JavaScript Objects
HTML DOM Objects
JavaScript How To

« PreviousNext Chapter »
Scripts in HTML must be inserted between <script> and </script> tags.

Scripts can be put in the <body> and in the <head> section of an HTML page.

The <script> Tag

To insert a JavaScript into an HTML page, use the <script> tag.

The <script> and </script> tells where the JavaScript starts and ends.

The lines between the <script> and </script> contain the JavaScript:

<script>
alert("My First JavaScript");
</script>
You don't have to understand the code above. Just take it for a fact, that the browser will interpret and execute the JavaScript code between the <script> and </script> tags. 

   Old examples may have type="text/javascript" in the <script> tag. This is no longer required. JavaScript is the default scripting language in all modern browsers and in HTML5.

JavaScript in <body>

In this example, JavaScript writes into the HTML <body> while the page loads:

Example

<!DOCTYPE html>
<html>
<body>
.
.
<script>
document.write("<h1>This is a heading</h1>");
document.write("<p>This is a paragraph</p>");
</script>
.
.
</body>
</html>

Try it yourself »

JavaScript Functions and Events

The JavaScript statements in the example above, are executed while the page loads.

More often, we want to execute code when an event occurs, like when the user clicks a button.

If we put JavaScript code inside a function, we can call that function when an event occurs.

You will learn much more about JavaScript functions and events in later chapters.

JavaScript in <head> or <body>

You can place an unlimited number of scripts in an HTML document.

Scripts can be in the <body> or in the <head> section of HTML, and/or in both.

It is a common practice to put functions in the <head> section, or at the bottom of the page. This way they are all in one place and do not interfere with page content.

A JavaScript Function in <head>

In this example, a JavaScript function is placed in the <head> section of an HTML page.

The function is called when a button is clicked:

Example

<!DOCTYPE html>
<html>
<head>
<script>
function myFunction()
{
document.getElementById("demo").innerHTML="My First JavaScript Function";
}
</script>
</head>

<body>

<h1>My Web Page</h1>

<p id="demo">A Paragraph</p>

<button type="button" onclick="myFunction()">Try it</button>

</body>
</html>


Try it yourself »

A JavaScript Function in <body>

In this example, a JavaScript function is placed in the <body> section of an HTML page.

The function is called when a button is clicked:

Example

<!DOCTYPE html>
<html>
<body>
<h1>My Web Page</h1>

<p id="demo">A Paragraph</p>

<button type="button" onclick="myFunction()">Try it</button>

<script>
function myFunction()
{
document.getElementById("demo").innerHTML="My First JavaScript Function";
}
</script>

</body>
</html>


Try it yourself »

	 The JavaScript is placed at the bottom of the page to make sure it cannot be executed after the <p> element is created.

External JavaScripts

Scripts can also be placed in external files. External files often contain code to be used by several different web pages.

External JavaScript files have the file extension .js.

To use an external script, point to the .js file in the "src" attribute of the <script> tag:

Example

<!DOCTYPE html>
<html>
<body>
<script src="myScript.js"></script>
</body>
</html>

Try it yourself »
You can place the script in the <head> or <body> as you like. The script will behave as if it was located exactly where you put the <script> tag in the document.
	 External scripts cannot contain <script> tags.


« PreviousNext Chapter »

W3Schools' Online Certification

The perfect solution for professionals who need to balance work, family, and career building.

More than 10 000 certificates already issued!

Get Your Certificate »

The HTML Certificate documents your knowledge of HTML.

The CSS Certificate documents your knowledge of advanced CSS.

The JavaScript Certificate documents your knowledge of JavaScript and HTML DOM.

The jQuery Certificate documents your knowledge of jQuery.

The XML Certificate documents your knowledge of XML, XML DOM and XSLT.

The ASP Certificate documents your knowledge of ASP, SQL, and ADO.

The PHP Certificate documents your knowledge of PHP and SQL (MySQL).

w3schools.com
on Facebook

WEB HOSTING
WEB BUILDING
W3SCHOOLS EXAMS
Get Certified in:
HTML, CSS, JavaScript, jQuery, XML, PHP, ASP
STATISTICS
Browser Statistics
Browser OS
Browser Display
SHARE THIS PAGE




Top 10 Tutorials

» HTML Tutorial
» HTML5 Tutorial
» CSS Tutorial
» CSS3 Tutorial
» JavaScript Tutorial
» jQuery Tutorial
» SQL Tutorial
» PHP Tutorial
» ASP.NET Tutorial
» XML Tutorial
Top 10 References

» HTML/HTML5 Reference
» CSS 1,2,3 Reference
» CSS 3 Browser Support
» JavaScript
» HTML DOM
» XML DOM
» PHP Reference
» jQuery Reference
» ASP.NET Reference
» HTML Colors
Examples

» HTML Examples
» CSS Examples
» XML Examples
» JavaScript Examples
» HTML DOM Examples
» XML DOM Examples
» AJAX Examples
» ASP.NET Examples
» Razor Examples
» ASP Examples
» SVG Examples	
Quizzes

» HTML Quiz
» XHTML Quiz
» CSS Quiz
» JavaScript Quiz
» jQuery Quiz
» XML Quiz
» ASP Quiz
» PHP Quiz
» SQL Quiz
Color Picker

 
Statistics

» Browser Statistics
» Browser OS
» Browser Display

 REPORT ERROR | HOME | TOP | PRINT | FORUM | ABOUT
W3Schools is optimized for learning, testing, and training. Examples might be simplified to improve reading and basic understanding.
Tutorials, references, and examples are constantly reviewed to avoid errors, but we cannot warrant full correctness of all content.
While using this site, you agree to have read and accepted our terms of use and privacy policy.
Copyright 1999-2012 by Refsnes Data. All Rights Reserved.

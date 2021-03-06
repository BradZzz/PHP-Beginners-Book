## What is HTML
The first component of any web page is the tag-based markup language of HTML. The Hyper Text Markup Language (HTML) has a sordid history but has come into its own in the last few years. After a lengthy experimentation with the XML-based XHTML variant the industry has accepted that HTML is the future of the web.

Markup defines the structure and outline of a document and offers a structured content. Markup is not intended to define the look and feel of the content on the page beyond rudimentary concepts such as headers, paragraphs, and lists. The presentation attributes of HTML have all been deprecated and style should be contained in style sheets.

HTML stands for *HyperText Markup Language* and was first mentioned way back in 1991 by Tim Berners-Lee and originally consisted of 20 elements.  Since then it has grown constantly adding form, tables, image maps and spawned CSS as a way to separate layout from presentation.  HTML itself is composed of several components, including elements, and their attributes as well as character-based data types, character references and entity references.  We will get into each of these components more in-depth later on.

Some people refer to elements as tags (e.g., "the P tag"). Remember that the element consists of a start tag, content, and an end *tag*, and the tag (be it start or end tag) is a component of the element. For instance, the HEAD element is always present, even though both start and end HEAD tags may be missing in the markup.

## Why learn HTML
The first question you are probably asking yourself is 'Why do I need to learn HTML?  I write PHP.  Doesnt that generate HTML?'

Yes, however it can only be helpful if you have a basic understanding of what HTML is and how it works.  Not only that but HTML is what each and every browser uses to render a document. Whether or not that document is generated using PHP, ASP, JSP or some other server-side based language or even if it's generated by Javascript, at some point in the life cycle HTML is created and given to the browser to display.

HTML is the building block of the web.  It is used to define how a document should be laid our or displayed.  Languages like Javascript were created to manipulate the elements of HTML and CSS is used to define or alter how a particular element is displayed or renders.

Because of this it is vital to have at least a basic understanding of HTML, how it works and what it does.  
## How are we going to learn this?
HTML is also probably the easiest of the so called _web languages_.  One of the reasons for this is the fact there is no logic or programming involved.  You just need to learn the elements and how they work.  Another is because there is a multitude of ways to mark up a document to achieve the desired outcome.  You technically don't **have** to use a `<p>` element to designate a paragraph, you can use a `<div>` or some other block level element.

The goal with this chapter is to not only give you a solid foundation of information on what the elements are and how to use them but also when and where they should be used.  It is infinitely better to use the `<p>` element to delineate a a paragraph rather than the `<div>`.

To help with this we will be building a typical blog page as we go along.  It will be based on a live site and if you have a blog running you can easily adapt it to your site if you wish, although you will probably want to make some styling changes, but that's another chapter.
## Tools
Writing, editing and testing HTML is incredibly easy, and chances are you already have everything you need.  HTML is unique among other the various other web technologies in the sense that the only think you need to build a site is a computer, a text editor and a browser.  Something as simple as vi or Notepad will suffice.  You don't need a server or any special software at all. You don't even need web server software like Apache or IIS. You can simply save the file and open it directly in your browser. 
## Basic Structure
All HTML based documents are the some.  They are composed of tags that define parts of the document, everything from a chunk of text that should be bolded to an entire area of the page that contains tabular data.
HTML uses elements to markup certain portions of text.  These can include headings, subtitles, bold or underlined text and, of course, links. HTML documents read from left to right and top to bottom. 

Elements are composed of tags (with attributes) and text. Tags are the parts of the document you see enclosed in the &lt; and &gt;. For example here is a paragraph element:

	<p>This is the first paragraph.</p>
	
In this example the `<p>` and `</p>` are the tags, they are used to delineate the text contained within as a paragraph. Something worth pointing out here is that you don't have to put everything on a single line.  The code above works just as well as this:

	<p>
		This is the first paragraph
	</p>
	
In fact the indentation isn't needed either, it's there for readability.  Keep in mind someone will have to edit this in the future.  It's helpful to do everything you can not to piss off your future self.

All tag formats are the same. They begin with a less-than sign: &lt; and end with a greater-than sign: &lt;. Always. No exceptions. What goes inside the < and > is the tag name. Learning HTML is learning the specific tags needed.

Not all elements have both an opening and closing piece.  For example `<br>` doesn't have a corresponding `</br>`, neither does `<hr>`.  


### Bare Minimum
HTML pages can be as simple or complex as you want.  Everything from

	<head>
		<body>
			Hello World!
		</body>
	</head>

But this isn't going to give you a very useful site.  
#### DocType
If a webpage is missing a `<DOCTYPE>` tag or has some sort of “transitional” doctype tag, the page will be rendered in what is called 'Quirks' mode.  For example if you are using IE7 and run across a page that has no doctype specified, IE7 will assume it's an old, outdated page, and will render the page just as it looked in IE6.  That's quirks mode.  It's also somewhat unpredictable.

So it is important to have a doctype tag if you want your webpage to display in Standards mode, as expected.

As a general rule you want to always build for Standards mode.  

	<!doctype html>
	
#### Head
the head of the document is where the title and meta information will go.  Generally you would put any CSS styles, script tags, and link tags to external files.  It is no longer a requirement to put them here (it was never a *requirement*, but has always been strongly encouraged)

##### Meta Tags
The Meta tag, along with the link tag, are the unique in that they are the only HTML tags that require neither a closing tag or a closing / at the end of the tag and are still considered syntactically correct.

The other thing about meta tags are they are the only tag that, generally speaking, has no effect on the layout or processing of the page, they are used to give information about the page and/or site being viewed.
The meta tag is essentially a key/value pair, and each tag can only contain one pair of values.  For example if you wanted search engines or others to know who the author of a site is you could use:
	
	<meta name=author content="BostonPHP Group">
	
Other common names are 

* application name - 
* description - 
* generator - string that identifies one of the software packages used to generate the document.  Should not be used on hand-authored pages.
* keywords -  set of comma-separated tokens, each of which is a keyword relevant to the page

Here is what a tool called "SiteMaker 2000" could include in its output, in the page's head element, to identify itself as the tool used to generate the page:

	<meta name=generator content="SiteMaker 2000 v8.2">
	
You are not required to use any of these metadata names and can make up your own, however it is strongly encouraged to use the pre-defined ones since every browser and software packages used to build sites knows about them and can use them.  The best solution is to use a combination of pre-defined and user-defined names.  Going back to the SiteMaker 2000 example above it could easily be written as such:

	<meta name=generator content="SiteMaker 2000">
	<meta name=version content="8.2">

#### Body
	<!DOCTYPE html>
 	<html>
 	<head>
 		<title>
 			This is the title of the page.
 		</title>
 	</head>
 	<body>
 		The body text goes here.
 	</body>
 	</html>



##### Headers
	<h1>Heading1</h1>
	<h2>Heading2</h2>
	<h3>Heading3</h3>
	<h4>Heading4</h4>
	<h5>Heading5</h5>
	<h6>Heading6</h6>
Header tags are block-level elements, so they put in line breaks for you. No other markup allowed inside heading tags.
##### div

Prior to 
## Forms
## Images
## Links
## Lists
## Tables
###Tables should not be used for layout
For several years, web designers used tables as the only way to structure web pages, and in a lot of cases they were badly overused. For complicated sites, it wasn't uncommon to have nested tables sometimes be 4 - 5 levels deep.  A nightmare for anyone trying to maintain or update that site.  As with the famous spacer.gif a majority of what tables do for layout can, and should, be done using CSS.  

HTML tables should only be used for rendering data that belongs naturally in a grid or in other words where the data describe a number of objects that have the same properties.  For example if it makes sense to display the data in Microsoft Excel, use a table.

In addition to all this, there are few other good reasons not to use tables for layout:

* Tables tend to 'break' on various browsers (IE being one notable culprit)
* Tables greatly increase the HTML/content ratio, meaning that for each table there is an addition 10 - 14 characters used, even if the 'content' is an image. And that's just for a single cell!
* Tables create accessibility nightmares.  Because tables are inherently meant to be read left to right one row at a time, using them for layout can cause screen readers to read content out of order and cause confusion for the users.

###Correct Semantic use of Tables in HTML
It is true that there remain a few things that are easier to do using tables.
The main benefit of tables is that all cells in a row, and all cells in a column, stretch together as the row or column stretches.
This effect is sometimes achievable in CSS, sometimes achievable with difficulty, and sometimes impossible.

###Table Basics 
The basic elements of tables are:

	<table> </table>
The opening and closing table tags.

	<thead> </thead>
The start and end of the table head section, which includes column headers

	<th> </th>
A table heading cell, which is a column header or row header

	<tbody> </tbody>
The start and end of the main body of the table, which contains the actual data

	<tr> </tr>
Table row; used in both the table head and table body

	<td> </td>
Table cell (stands for "table data"), which holds the actual data

## HTML5
HTML5 is the latest version of HTML and XHTML. The HTML5 draft specification defines a single language that can be written in HTML and XML. It is an attempt to solve several issues found in previous iterations of HTML and addresses the needs of Web Applications, an area previously not adequately covered by HTML. 

### header
### nav
### article
### section
### footer

## Semantics
Anyone who has written code (of any kind) for any length of time knows there are two types of code that is painful to work on.  Someone elses code, and code you wrote months ago.

There are generally two schools of thought on how to rectify this, comment your code or make your code 'self commenting'.  Personally I don't like putting comments in HTML and have never seen 'self commenting' code multiple people could understand easily.

Enter the idea of **Semantic markup**

In the most simplistic terms semantic markup is:

>markup that has meaning; markup that describes the content it contains, rather than what that content should look like. 

In other words, let the HTML help you to define the *structure* of the document.

To use semantic markup properly you have to think about your content first. For example use `<ul>` where you have lists, us `<p>` instead of `<div>` for content separation and using `<table>` for tabular data (not layout).

### Benefits
#### Efficieny
Semantic Markup also lets you establish a common vocabulary for your site markup. Other developers don't need to take extra time to consider what markup should be used for different types of content. A paragraph gets a `<p>`. An ordered list gets an `<ol>` etc,.

By creating and following standards, and by eliminating unnecessary `<div>`s, `<span>`s and nested `<table>`s, your HTML markup is more readable. And being more readable means it's easier to troubleshoot, debug and maintain. This can also result in a smaller overall page size, which, in turn means faster page load which mean happier users. Remember, not everyone has high-speed broadband access and not everyone uses the latest and greatest technologies.

#### Accessibility
A huge benefit of using semantic markup is that it provides a solid foundation for building an accessible site. Technologies such as screen readers navigate sites according to structure, and generally from top down. For example, a site marked up with heading elements (`<h1>`-`<h6>`) to convey a hierarchical content structure gives screen reader users the ability to navigate to different sections within the document.

WCAG 2.0 guidelines encourage semantic markup, not only for page structure, but also for lists (`<ul>`, `<ol>`, `<dl>`) and special text that requires emphasis (`<strong>`, `<blockquote>`, `<abbr>`). Further, these guidelines discourage the use of `<table>` elements for anything other than tabular data.

#### Readability
Semantic markup is extremely portable.  If can be used by HTML renderers (typically a web browser) but also screen readers, mobile devices and 

One of the more challenging aspects of writing semantic markup is figuring out the proper elements to use. For some content, it is immediately clear that a `<p>` should be used or an `<h1>`. In other cases it's not so clear and can take a few tries before it looks and _feels_ right.
### When to use
In general, always. Let me use a chunk of code from mu website to show a couple examples. I'll show what it looked like before and what it looks like after adding semantic markup

#### Before
	<div>
		<p><a href="/" title="Home">Home</a></p>
		<p><a href="/about/" title="About">About</a></p>
		<p><a href="/archives/" title="Archives">Archives</a></p>
		<p><a href="/scribblings-2/" title="Scribblings">Scribblings</a></p>
	</div>

#### After 
	<div class="menu">
		<ul>
			<li><a href="/" title="Home">Home</a></li>
			<li class="page_item page-item-2"><a href="/about/" title="About">About</a></li>
			<li class="page_item page-item-651"><a href="/archives/" title="Archives">Archives</a></li>
			<li class="page_item page-item-573"><a href="/scribblings-2/" title="Scribblings">Scribblings</a></li>
		</ul>
	</div>

Notice that the overall layout didn't change that much.  The `<p>`s were changed to `<li>`s and that was pretty much it.  In this case (and most really) it's not the *how* that you really have to think about, but the *why*. The the first example those links could have been anything.  A collection of random links collected from the net or a set of XXX, or anything really.  In this example however, I knew were a essentially a menu of internal navigation links, so it made sense to group them together making an ideal candidate for an unordered list element (`<ul>`).
### HTML 5
	HTML5 has dramatically helped the semantic landscape by adding a number of new elements that can, and should reduce the number of `<divs>` and `<spans>` in your document. With the new `<header>`, `<section>`, `<footer>`, `<nav>`, `<article>`, and `<aside>` elements you can eliminate things such as `<div id="nav">`, `<div id="post_content">`, and `<div id="sidebar">`.  

	Let's revist the example of using the menu elements and see what it looks like if we use the _`<nav>_ element:

		<nav>
			<ul>
				<li><a href="/" title="Home">Home</a></li>
				<li class="page_item page-item-2"><a href="/about/" title="About">About</a></li>
				<li class="page_item page-item-651"><a href="/archives/" title="Archives">Archives</a></li>
				<li class="page_item page-item-573"><a href="/scribblings-2/" title="Scribblings">Scribblings</a></li>
			</ul>
		</nav>

	It's a subtle difference in this case, changing the `<div>`'s to `<nav>` but the meaning has become clearer and anyone that looks at the code will know instantly that the items in the `<nav>` elements are meant to be navigation.

		<html>
			<head>
			</head>
			<body>
				<header>
					<nav>
					</nav>
				</header>
				<section>
					<article>
						<header>
						</header>
						<aside>
						</aside>
					</article>
					<article>
						<header>
						</header>
					</article>
				</section>
				<section>
					<aside>
					</aside>
				</section>
				<footer>
				</footer>
			</body>
		</html>


[^1]:  
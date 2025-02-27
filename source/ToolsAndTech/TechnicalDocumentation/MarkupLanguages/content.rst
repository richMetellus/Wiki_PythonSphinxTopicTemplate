Markup Languages 
#################

Intro 
******

**What is a markup language**

A :term:`markup language` 

* is a text-encoding system which specifies the structure 
  and formatting of a document and potentially the relationships among its parts (Wikipedia).

    * Example of markup languages: hypertext markup language (.html), markdown (.md), extensible markup 
      language (.xml), restructured text (.rst), LaTeX (.tex), AsciiDoc

The keyword point is that a markup language uses **plain text** and contains no binary 
information.

There may be variations of a markup language. 

* For example **Markdown** was originally conceptualized 
  as a lightweight representation of html. 
  Markdown syntax is not extensible. Eventually many different organizations 
  have created various projects to  extend markdown syntax. 
  This lead to the ecosystem being fragmented. 

    * Today we have
  
        * Github-Flavored markdown, 
        * CommonMark
        * MultiMarkdown
        * Markdown for the component era (.mdx)
        * ... much more

For each markup language, there exist a parser and/or a compiler that understands 
that language's syntax and render it properly.
    
* ex: for HTML -> browser engine is the parser.

Explore Some Markup Languages
******************************

.. toctree::
   :glob:
   :maxdepth: 1
   :numbered:

   RST/content
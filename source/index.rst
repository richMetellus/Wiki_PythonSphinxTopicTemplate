
.. .. contents:: 
..    :depth: 4

Richelin's Digital Notebook
##############################

**Release Date**: |release_date|

|

Welcome to Richelin's Digital Notebook ( Knowledge Library) !!!

What is this document?

This doc 

* is the most basic template needed to start documenting project or taking notes 
  digitally.

    * you can use it for classes/courses note taking, or to create 
      scientific document for publish assuming you have the right 
      extensions in place and have configured the project according to your needs.
  
* it uses Python Sphinx as a static-html or pdf document generator by only using markdown or
  restructured text as the markup language. 

* This epitomizes the "documentation as code philosophy" thus making it easier to put these 
  document under version control (SVN, Git-SCM) as needed. **Note**: Using a source control
  management software such as Git can provide flexibility on how to manage many different 
  files, pull docs from many git source and publish the documentation outputs to a platform 
  such as sharepoint or other hosting platform such as `Read the Docs <https://about.readthedocs.com/>`_

* This makes it possible for me to share my notes with peers and spread the 
  knowledge (on sharepoint for example)

* This doc is similar to a forever evolving blog.
* This document heavily used tree structure/hierarchy for each page and make it easier to 
  mindmap the information or jump to only relevant section. This technique was 
  very useful to when I was in college. It made it easier for me to review or only 
  study the night before an exam and still confident enough to get a good grade. 
  
  Please use theme that provide navigation tab(s).

* It is also possible to use Jupyter Notebook with markdown and use 
  `Jupyter Book <https://jupyterbook.org/en/stable/intro.html>`_
  to create beautiful book from the ``*.ipynb`` jupyter files.

Developer Guide: Build The project
******************************************

There are various theme that are installed within the virtual environment of the 
project.

* `Cloud sphinx theme (cloud_sptheme) <https://cloud-sptheme.readthedocs.io/en/latest/index.html>`_
* `Piccolo theme <https://github.com/piccolo-orm/piccolo_theme>`_
* `Sphinx book theme <https://sphinx-book-theme.readthedocs.io/en/stable/>`_

Dependencies
================

**Sphinx project dependencies**

This project require a few dependencies.

#. python
#. pip
#. pipenv

Although some dependencies (python packages) are being kept tracked of via Pipefiles and can be 
automatically installed, others require some executable to be on the user's build
machine.

* The **drawio extension** depends on

    1. `diagrams.net <https://www.diagrams.net/>`_ executable to be on 
       user's machine.

* The **plantuml sphinx extension** depends on a
    
    *  `plantuml.jar` that requires `java -jar` command so you'll need the java
       `jre <https://www.java.com/en/download/>`_ on your system

        *  The sphinx-needs has some instruction on how to install plantuml to work with sphinx
           `plantuml <https://sphinx-needs.readthedocs.io/en/latest/installation.html>`_

  

All the rest can be instantiated by running ``pipenv install`` without argument from the top
directory. This command will create a virtual environment if one does not exist already
and see there is a Pipefile.lock and install the required packages and their dependencies.

You can start the virtual environment by running ``pipenv shell`` to spawn
your current shell, once the virtual environment is activated then run any command 
as you normally would. Or you can run specific command using ``pipenv run <command-you-want>``
Example, ``pipenv run make livehtml`` will start building the python sphinx
documentation project and start a local web server and will watch for changes
as you edit your document source.

Knowledge Bank 
*****************

**Tools and/or Technology**

.. toctree::
   :caption: Technical documentation
   :maxdepth: 2

   ToolsAndTech/TechnicalDocumentation/content

.. toctree::
    :caption: Topic Template
    :glob:
    :maxdepth: 1

    Wiki_TopicTemplate/content

Indices, glossary, and tables
*********************************

.. toctree::
    
    glossary
    ToolsAndTech/TechnicalDocumentation/glossary.rst

.. include:: includes.rst

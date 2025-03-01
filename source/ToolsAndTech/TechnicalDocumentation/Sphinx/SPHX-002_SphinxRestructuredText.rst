Sphinx and RestructuredText Cheatsheet
#######################################

**Scope and Purpose**

This document is where I will keep track of the various reStructuredText (rST)
directives and syntax that I commonly use in my Sphinx documentation projects.
This is not meant to be a comprehensive guide to reStructuredText, or Sphinx.

.. note:: A comprehensive guide was written for RestructuredText (rST, reST)
    
    .. seealso:: :ref:`RestructuredText Cheatsheet created in this project 
        <rstCheatsheetGuide>`
    
    .. seealso:: `Sphinx documentation <https://www.sphinx-doc.org/en/master/usage/index.html>`_

Sphinx Only Directives & Roles 
********************************

The directives below are only available in Sphinx and not in the classic
reStructuredText (rST)/docutils.

Code Block & Syntax Highlighting
==================================

The ``code-block`` directive is used to display block of code 
in your documentation just like the docutils rST ``code`` directive, but 
a more powerful version.
Through pygments, syntax highlighting is available
for multiple programming languages.

* Syntax::

    .. code-block:: <language>
       :option: value

       <your code here>
    
* ``<language>``:  The programming language for syntax highlighting 
  (e.g., python, bash, console javascript, C, C++, json, etc...).
 
* ``:option: value`` : Optional settings like ``linenos`` for line numbers, 
  ``emphasize-lines`` for highlighting lines, ``lineno-start`` to specify the 
  starting line number for the code being displayed.

.. note:: By default, code blocks will use python syntax highlighting.
    
+----------------------------------------------------+----------------------------------------------------+
| Raw Text                                           | Rendered as                                        |
+====================================================+====================================================+
| ::                                                 |                                                    |
|                                                    |                                                    |
|    .. code-block:: python                          |    .. code-block:: python                          | 
|                                                    |                                                    |
|        def greet(name):                            |        def greet(name):                            |
|            print(f"Hello, {name}!")                |            print(f"Hello, {name}!")                | 
|                                                    |                                                    |
+----------------------------------------------------+----------------------------------------------------+
| ::                                                 |                                                    | 
|                                                    |                                                    |
|   .. code-block:: C                                |   .. code-block:: C                                |                         
|                                                    |                                                    |       
|       #include <stdio.h>                           |       #include <stdio.h>                           |                             
|                                                    |                                                    | 
|       // Function to greet a user by name          |       // Function to greet a user by name          |                                              
|       void greet(const char *name) {               |       void greet(const char *name) {               |                                         
|           printf("Hello, %s!\n", name);            |           printf("Hello, %s!\n", name);            |                                            
|       }                                            |       }                                            |            
|                                                    |                                                    |       
+----------------------------------------------------+----------------------------------------------------+
| ::                                                 |                                                    |
|                                                    |                                                    |
|   .. code-block:: python                           |   .. code-block:: python                           |                            
|      :emphasize-lines: 2,4                         |      :emphasize-lines: 2,4                         |                              
|      :linenos:                                     |      :linenos:                                     |                  
|                                                    |                                                    |   
|       def factorial(n):                            |       def factorial(n):                            |                           
|           if n == 0:                               |           if n == 0:                               |                        
|               return 1                             |               return 1                             |                          
|           return n * factorial(n - 1)              |           return n * factorial(n - 1)              |                                         
|                                                    |                                                    |   
|                                                    |                                                    |   
+----------------------------------------------------+----------------------------------------------------+


+------------------------------------------------------------------------------+------------------------------------------------------------------------------+
| Raw Text                                                                     | Rendered as                                                                  |
+==============================================================================+==============================================================================+
| ::                                                                           |                                                                              |
|                                                                              |                                                                              |
|    .. code-block:: python                                                    |    .. code-block:: python                                                    |                                  
|        :emphasize-lines: 6-7, 17                                             |        :emphasize-lines: 6-7, 17                                             |                                        
|        :lineno-start: 10                                                     |        :lineno-start: 10                                                     |                                
|                                                                              |                                                                              |       
|        def fibonacci(n: int, memo: dict = {}) -> int:                        |        def fibonacci(n: int, memo: dict = {}) -> int:                        |                                                             
|            """                                                               |            """                                                               |                      
|            Calculate the nth Fibonacci number using manual memoization.      |            Calculate the nth Fibonacci number using manual memoization.      |                                                                               
|                                                                              |                                                                              |       
|            Args:                                                             |            Args:                                                             |                        
|                n (int): The position in the Fibonacci sequence.              |                n (int): The position in the Fibonacci sequence.              |                                                                       
|                memo (dict): A dictionary to store computed Fibonacci numbers.|                memo (dict): A dictionary to store computed Fibonacci numbers.|                                                                                     
|                                                                              |                                                                              |       
|            Returns:                                                          |            Returns:                                                          |                           
|                int: The nth Fibonacci number.                                |                int: The nth Fibonacci number.                                |                                                     
|            """                                                               |            """                                                               |                     
|                                                                              |                                                                              |                                                                   
|            if n < 0:                                                         |            if n < 0:                                                         |                      
|                raise ValueError("Input must be a non-negative integer.")     |                raise ValueError("Input must be a non-negative integer.")     |                                                                          
|            if n <= 1:                                                        |            if n <= 1:                                                        |                      
|                return n                                                      |                return n                                                      |                          
|            if n not in memo:                                                 |            if n not in memo:                                                 |                              
|                memo[n] = fibonacci(n - 1, memo) + fibonacci(n - 2, memo)     |                memo[n] = fibonacci(n - 1, memo) + fibonacci(n - 2, memo)     |                                                                          
|            return memo[n]                                                    |            return memo[n]                                                    |                          
|                                                                              |                                                                              |  
|        # Example usage                                                       |        # Example usage                                                       |                          
|        if __name__ == "__main__":                                            |        if __name__ == "__main__":                                            |                                  
|            n = 7                                                             |            n = 7                                                             |                  
|            print(f"The {n}th Fibonacci number is: {fibonacci(n)}")           |            print(f"The {n}th Fibonacci number is: {fibonacci(n)}")           |                                                                      
|                                                                              |                                                                              |  
+------------------------------------------------------------------------------+------------------------------------------------------------------------------+

``:ref:`` Role
===============

The ``:ref:`` inline markup

* is a role that is commonly use in Sphinx to create cross-references 
  to arbitrary locations in any document in the project.

* is very useful for documents, multi page linkage.

To create one the standard reStructuredText target labels are used.

* syntax to create a target label::

    .. _target-label:

* syntax to reference one::

    :ref:`label alt text <target-label>`

    Or 

    :ref:`target-label`

+--------------------------------------------------------------+--------------------------------------------------------------+
| Raw Text                                                     | Rendered as                                                  |
+==============================================================+==============================================================+
| ::                                                           |                                                              |
|                                                              |                                                              |
|                                                              |                                                              |      
|    .. _example-section:                                      |    .. _example-section:                                      |                              
|                                                              |                                                              |      
|    Use https://www.lipsum.com/ to generate random text.      |    Use https://www.lipsum.com/ to generate random text.      |                                                              
|                                                              |                                                              |      
|    Lorem ipsum dolor sit amet, consectetur adipiscing elit.  |    Lorem ipsum dolor sit amet, consectetur adipiscing elit.  |                                                                   
|    Mauris aliquam orci et nibh ultricies, nec venenatis nisl |    Mauris aliquam orci et nibh ultricies, nec venenatis nisl |                                                                    
|    ullamcorper. Fusce dignissim dui sed augue ultrices, eget |    ullamcorper. Fusce dignissim dui sed augue ultrices, eget |                                                                    
|    posuere lectus vulputate. Praesent quis sagittis turpis.  |    posuere lectus vulputate. Praesent quis sagittis turpis.  |                                                                   
|    Morbi vestibulum dictum libero, ut bibendum ex. Phasellus |    Morbi vestibulum dictum libero, ut bibendum ex. Phasellus |                                                                    
|    aliquam facilisis neque, ut ultricies risus ultricies id. |    aliquam facilisis neque, ut ultricies risus ultricies id. |                                                                    
|    Sed vel venenatis dui. Nullam efficitur sem eget nunc     |    Sed vel venenatis dui. Nullam efficitur sem eget nunc     |                                                                
|    rhoncus, id posuere elit pretium. Cras sodales sagittis   |    rhoncus, id posuere elit pretium. Cras sodales sagittis   |                                                                   
|    est eu pellentesque. Cras consectetur lacus est,          |    est eu pellentesque. Cras consectetur lacus est,          |                                                            
|    placerat ante fermentum in. Sed euismod, elit id          |    placerat ante fermentum in. Sed euismod, elit id          |                                                           
|    accumsansodales dignissim, dolor eros iaculis diam, et    |    accumsansodales dignissim, dolor eros iaculis diam, et    |                                                                 
|    accumsan magna mi molestie metus. Donec a                 |    accumsan magna mi molestie metus. Donec a                 |                                                    
|    turpis consequat, auctor ex scelerisque.                  |    turpis consequat, auctor ex scelerisque.                  |                                                  
|                                                              |                                                              |
|    Refer to the :ref:`Example Section <example-section>`     |    Refer to the :ref:`Example Section <example-section>`     |                                                                
|    for more details.                                         |    for more details.                                         |                           
|                                                              |                                                              |      
+--------------------------------------------------------------+--------------------------------------------------------------+

``:doc:`` Role
===============
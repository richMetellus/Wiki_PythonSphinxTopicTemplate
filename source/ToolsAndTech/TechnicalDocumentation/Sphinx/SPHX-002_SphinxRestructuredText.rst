Sphinx and RestructuredText Cheatsheet
#######################################

.. note:: A comprehensive guide was written for RestructuredText (rST, reST)
    
    .. seealso:: :ref:`RestructuredText Cheatsheet <rstCheatsheetGuide>`

Code Block & Syntax Highlighting
**********************************

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
| ::                                                                           | ::                                                                           |
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


---
ID: 743
post_title: Python Modules and Packages
author: admin
post_excerpt: ""
layout: post
permalink: >
  https://cscourses.online/python/python-modules-and-packages/
published: true
post_date: 2019-03-13 13:10:12
---
<!DOCTYPE html>
<html>
  <head>
  </head>
  <body>
    <h3>Python Module</h3>
    <p>Modules are processed with two statements: </p>
    <ul>
      <li><b>import</b> Lets a importer fetch a module as a whole </li>
      <li><b>from</b> Allows a importer to fetch particular names from a module</li>
    </ul>
    <pre>&gt;&gt;&gt; import module1 # Get module as a whole (one or more)
&gt;&gt;&gt; module1.printer('Hello world!') # Qualify to get names
Hello world!

&gt;&gt;&gt; from module1 import printer # Copy out a variable (one or more)
&gt;&gt;&gt; printer('Hello world!') # No need to qualify name
Hello world!  
    </pre>
    <p>Python’s module search path is:</p>
    <ul>
      <li>The home directory of the program</li>
      <li>PYTHONPATH directories (if set)</li>
      <li>Standard library directories</li>
      <li>The contents of any .pth files (if present)</li>
      <li>The site-packages home of third-party extensions</li>
    </ul>
    <h3>Python Module Packages</h3>
    <p>In Python, an import can name a directory path. A directory of Python
      code is said to be a package, so such imports are known as package
      imports.</p>
    <pre>import dir1.dir2.module
from dir1.dir2.module import x
 </pre>
  </body>
</html>
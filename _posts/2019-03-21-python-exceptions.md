---
ID: 807
post_title: Python Exceptions
author: admin
post_excerpt: ""
layout: post
permalink: >
  https://cscourses.online/python/python-exceptions/
published: true
post_date: 2019-03-21 23:51:36
---
<!DOCTYPE html>
<html>
  <head>
    <meta http-equiv="content-type" content="text/html; charset=UTF-8">
    <title></title>
  </head>
  <body>
    <h2>Python Exceptions</h2>
    <h3>Python raise Statements</h3>
    <p>Exceptions can be raised by Python or by your program, and can be caught
      or not. To trigger an exception simply run a raise statement.</p>
    <pre>raise IndexError;</pre>
    <h3>Python try/except/finally Statements</h3>
    <p>Python raises exceptions whenever it detects errors in programs at
      runtime. You can catch and respond to the errors in your code,</p>
    <pre>&gt;&gt;&gt; try:
...   raise IndexError;
... except IndexError:
...   print("got exception")
... finally:
...   print("finally")
... 
got exception
finally
&gt;&gt;&gt; 
</pre>
  </body>
</html>
---
ID: 734
post_title: Python Functions and Generators
author: admin
post_excerpt: ""
layout: post
permalink: >
  https://cscourses.online/python/python-functions-and-generators/
published: true
post_date: 2019-03-13 04:10:00
---
<!DOCTYPE html>
<html>
  <head>
    <meta http-equiv="content-type" content="text/html; charset=UTF-8">
    <title></title>
  </head>
  <body>
    <h2>Python Functions and Generators</h2>
    <h3>Python def Statement</h3>
    <p>The def statement creates a function object and assigns it to a name.
      Function bodies often contain a return statement.</p>
    <pre>def name(arg1, arg2,... argN):
  ...
  return value</pre>
    <p>Name scope about function,</p>
    <ul>
      <li> Names assigned inside a def can only be seen by the code within that
        def. You cannot refer to such names from outside the function. </li>
      <li>Names assigned inside a def do not clash with variables outside the
        def, even if the same names are used elsewhere. </li>
      <li>If a variable is assigned inside a def, it is local to that function.
      </li>
      <li>If a variable is assigned in an enclosing def, it is nonlocal to
        nested functions. </li>
      <li>If a variable is assigned outside all def s, it is global to the
        entire file. </li>
    </ul>
    <p>Python global allows us to change names that live outside a def at the
      top level of a module file.&nbsp; Python nonlocal statement is almost
      identical but applies to names in the enclosing def ’s local scope, rather
      than names in the enclosing module.</p>
    <h3>Python Closure</h3>
    <p>Closure remembers values in enclosing scopes regardless of whether those
      scopes are still present in memory.</p>
    <pre>&gt;&gt;&gt; def maker(N):
  def action(X):
    return X ** N
  return action  
&gt;&gt;&gt; f = maker(2) # Pass 2 to argument N  
&gt;&gt;&gt; f(3)
9
&gt;&gt;&gt; f(4)
16</pre>
    <h3>Python lambda</h3>
    <p>Lambda expression creates a function to be called later, but it returns
      the function instead of assigning it to a name. This is why lambda s are
      sometimes known as anonymous functions.</p>
    <pre>lambda argument1, argument2,... argumentN : expression using arguments</pre>
    <p>Below is an example,</p>
    <pre>&gt;&gt;&gt; f = lambda x, y, z: x + y + z
&gt;&gt;&gt; f(2, 3, 4)
9</pre>
    <h3>Python Generators</h3>
    <p>Generator functions are like normal functions in most respects, and in
      fact are coded with normal def statements. However, when created, they are
      compiled specially into an object that supports the iteration protocol.
      And when called, they don’t return a result: they return a result
      generator that can appear in any iteration context.</p>
    <pre>&gt;&gt;&gt; def gensquares(N):
  for i in range(N):
    yield i ** 2  # Resume here later
>>> x = gensquares(4)
>>> next(x)
0
>>> next(x)
1
>>> next(x)
4</pre>
  </body>
</html>
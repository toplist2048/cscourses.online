---
ID: 734
post_title: Python Functions and Generators
author: admin
post_excerpt: ""
layout: post
permalink: >
  https://cscourses.online/uncategorized/python-functions-and-generators/
published: true
post_date: 2019-03-13 04:10:00
---
    <h3>Python def Statements</h3>
    <p>The def statement creates a function object and assigns it to a name.</p>
    <pre>def name(arg1, arg2,... argN):
  ...
  return value
</pre>
    <h3>Python Scope</h3>
    <p>Names assigned inside a def can only be seen by the code within that def.
      You cannot even refer to such names from outside the function. Names
      assigned inside a def do not clash with variables outside the def, even if
      the same names are used elsewhere. </p>
    <p>If a variable is assigned inside a def, it is local to that function. If
      a variable is assigned in an enclosing def, it is nonlocal to nested
      functions. If a variable is assigned outside all defs, it is global to the
      entire file.</p>
    <p><b>global</b> makes scope lookup begin in the enclosing module's scope
      and allows names there to be assigned. Scope lookup continues on to the
      built-in scope if the name does not exist in the module, but assignments
      to global names always create or change them in the module’s scope.</p>
    <p><b>nonlocal</b> restricts scope lookup to just enclosing defs, requires
      that the names already exist there, and allows them to be assigned. Scope
      lookup does not continue on to the global or built-in scopes.</p>
    <h3>Python Factory Functions: Closures</h3>
    <p>Factory functions (a.k.a. closures) are sometimes used by programs that
      need to generate event handlers on the fly in response to conditions at
      runtime.</p>
    <pre>&gt;&gt;&gt; def maker(N):
  def action(X): # Make and return action
    return X ** N # action retains N from enclosing scope
  return action
</pre>
    <h3>Python Arguments</h3>
    <p>Arguments are passed by automatically assigning objects to local variable
      names. Assigning to argument names inside a function does not affect the
      caller. Changing a mutable object argument in a function may impact the
      caller.</p>
    <p>Immutable arguments are effectively passed "by value". Mutable arguments
      are effectively passed "by pointer". </p>
    <p>Python caller argument matching,</p>
    <table>
      <thead>
        <tr>
          <td>Syntax</td>
          <td>Interpretation</td>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>func(value)</td>
          <td>Normal argument: matched by position</td>
        </tr>
        <tr>
          <td>func(name=value)</td>
          <td>Keyword argument: matched by name</td>
        </tr>
        <tr>
          <td>func(*iterable)</td>
          <td>Pass all objects in iterable as individual positional arguments</td>
        </tr>
        <tr>
          <td>func(**dict)</td>
          <td>Pass all key/value pairs in dict as individual keyword arguments</td>
        </tr>
      </tbody>
    </table>
    <p>Python function argument matching,</p>
    <table>
      <thead>
        <tr>
          <td>Syntax</td>
          <td>Interpretation</td>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>def func(name)</td>
          <td>Function Normal argument: matches any passed value by position or
            name</td>
        </tr>
        <tr>
          <td>def func(name=value)</td>
          <td>Function Default argument value, if not passed in the call</td>
        </tr>
        <tr>
          <td>def func(*name)</td>
          <td>Function Matches and collects remaining positional arguments in a
            tuple</td>
        </tr>
        <tr>
          <td>def func(**name)</td>
          <td>Function Matches and collects remaining keyword arguments in a
            dictionary</td>
        </tr>
        <tr>
          <td>def func(*other, name)</td>
          <td>Function Arguments that must be passed by keyword only in calls</td>
        </tr>
        <tr>
          <td>def func(*, name=value)</td>
          <td>Function Arguments that must be passed by keyword only in calls</td>
        </tr>
      </tbody>
    </table>
    <h3>Python Recursive Functions</h3>
    <p>Python supports recursive functions — functions that call themselves
      either directly or indirectly in order to loop.</p>
    <h3>Python Indirect Function Calls</h3>
    <p>Because Python functions are objects, you can write programs that process
      them generically. Function objects may be assigned to other names, passed
      to other functions, embedded in data structures, returned from one
      function to another, and more, as if they were simple numbers or strings.
      Function objects also happen to support a special operation: they can be
      called by listing arguments in parentheses after a function expression.</p>
---
ID: 729
post_title: Python Statements
author: admin
post_excerpt: ""
layout: post
permalink: >
  https://cscourses.online/python/python-statements/
published: true
post_date: 2019-03-13 03:54:56
---
    <h3>Python Assignment Statements</h3>
    <table>
      <thead>
        <tr>
          <td>Operation</td>
          <td>Interpretation</td>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>spam = 'Spam'</td>
          <td>Basic form</td>
        </tr>
        <tr>
          <td>spam, ham = 'yum', 'YUM'</td>
          <td>Tuple assignment (positional)</td>
        </tr>
        <tr>
          <td>[spam, ham] = ['yum', 'YUM']</td>
          <td>List assignment (positional)</td>
        </tr>
        <tr>
          <td>a, b, c, d = 'spam'</td>
          <td> Sequence assignment, generalized</td>
        </tr>
        <tr>
          <td>a, *b = 'spam'</td>
          <td>Extended sequence unpacking</td>
        </tr>
        <tr>
          <td>spam = ham = 'lunch' </td>
          <td>Multiple-target assignment</td>
        </tr>
        <tr>
          <td>spams += 42 </td>
          <td>Augmented assignment (equivalent to spams = spams + 42)</td>
        </tr>
      </tbody>
    </table>
    <h3>Python if Statements</h3>
    <p>The Python if statement is typical of if statements in most procedural
      languages</p>
    <pre>if test1: # if test
  statements1 # Associated block
elif test2: # Optional elifs
  statements2   
else: # Optional else
  statements3  
</pre>
    <h3>Python while Loops</h3>
    <p>Python's while statement repeatedly executes a block of statements as
      long as a test at the top keeps evaluating to a true value.</p>
    <pre>while test:
  statements
  if test: break # Exit loop now, skip else if present
  if test: continue # Go to top of loop now, to test1
else:
  statements # Run if we didn't hit a 'break'    
</pre>
    <p><b>break,</b> Jumps out of the closest enclosing loop (past the entire
      loop statement)</p>
    <p><b>continue,</b> Jumps to the top of the closest enclosing loop (to the
      loop’s header line)</p>
    <p><b>pass,</b> Does nothing at all: it’s an empty statement placeholder</p>
    <h3>Python for Loops</h3>
    <p>The Python for loop begins with a header line that specifies an
      assignment target, along with the object you want to step through.</p>
    <pre>for target in object: # Assign object items to target
  statements
  if test: break # Exit loop now, skip else
  if test: continue # Go to top of loop now
else:
  statements # If we didn't hit a 'break'
</pre>
    <h3>Python Iteration</h3>
    <p>The iterable object you request iteration for, is run by iter;</p>
    <p>The iterator object returned by the iterable that produces values during
      the iteration, whose __next__ is run by next and raises StopIteration when
      finished producing results.</p>
    <pre>&gt;&gt;&gt; l = [1,2,3,4]
&gt;&gt;&gt; i = iter(l)
&gt;&gt;&gt; next(i)
1
&gt;&gt;&gt; next(i)
2
&gt;&gt;&gt;
</pre>
    <h3>Python List Comprehension</h3>
    <p>List comprehensions are written in square brackets because they are
      ultimately a way to construct a new list. They begin with an arbitrary
      expression, which uses a loop variable. That is followed by the header of
      a for loop, which names the loop variable, and an iterable object (for x
      in L).</p>
    <pre>L = [x + 10 for x in L]
</pre>
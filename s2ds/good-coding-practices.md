---
layout: default
title: "S2DS Good Coding Practices"
date: 2014-08-05
tags: s2ds
---

# Good Coding Practices

[Ole Moeller-Nilsson](https://twitter.com/olly_mn) talked to us about
good coding practices.

## Introduction

- Ada Lovelace (1815-1852) is considered to be the first programmer
  due to her description of Babbage's analytical machine
- Code can be thought of as a means for communication:
  There is machine code understood by the computer, source code
  understood by humans, and a translation process (compilation)
  between the two.

## Programming Languages

A number of properties that distinguish programming languages are:

- types: untyped, statically/strongly typed, dynamically / weakly typed
- compiled languages rely on an explicit compilation step
- interpreted languages have no explicit compilation step
- procedural: sequential procedures
- object oriented
- aspect oriented: e.g. event logging
- functional: stateless, input / output pipelines constructed out of functions

## Code Quality

- Generally, good code is tested, well-written, etc.
- We should care about code quality since we write code for someone else
  where that someone else may be your employer, your colleagues, or in
  many cases your future self.
- A few examples of projects that have failed partly due to poor code
  quality:
      * [Taurus, London Stock Exchange](http://calleam.com/WTPF/?p=3474)
      * [LASCAD, London Ambulance Service](http://hoozy.com/pinchbeck/college/work/papers/dispatching_failure.htm)
- On the debate over scripting v. coding:
  Scripts are oftentimes prototypes for production code and we should
  therefore take the quality of scripts as seriously as that of code.

## Function and Variable Naming

- functions:
    * are actions in code
    * use verb and noun for naming (avoid 'do', 'be', 'perform' and other
      non-informative verbs)
    * be consistent about casing and your use of underscores
    * use one word per concept
    * do not abbreviate too much
- variables:
    * are 'things' hence use nouns
    * use prefix for context
    * see function naming
- classes:
    * are 'types of things'
    * use nouns
    * have each class encapsulate one thing only (this is more a matter of
      code architecture than naming I guess)

## Comments

- R.C. Martin: "Comments are always failures."
- comment only if you cannot make your code clearer otherwise
- comments should explain why not how
- use TODOs and FIXMEs for future reference
- highlight important places, comment unusual code
- do not comment past / removed code, nor conditions which really must
  be checked in your code

## Functions

- one function should do exactly one thing (keep them small)
- avoid side effects
- use few parameters as every parameter introduces questions
  (Why is the parameter needed? What are its effects? ...)
- avoid return arguments (TODO: why is this?)

## Classes

- are templates for objects
- package data and functions, i.e. permitted behavior
- have one concrete responsibility
- encapsulation:
    * encapsulate as much of the internals of your classes as possible
    * this keeps code that uses your class and your own code independent

## Code Layout

- write higher level functionality at the top of your file and
  implement specifics further below
- do not mix tabs and spaces as this messes up formatting in certain editors
- always check your language's style guide:
    * [Google C++ style guide](https://google-styleguide.googlecode.com/svn/trunk/cppguide.xml)
    * [Google Python style guide](https://google-styleguide.googlecode.com/svn/trunk/pyguide.html)
    * [Google R style guide](https://google-styleguide.googlecode.com/svn/trunk/Rguide.xml)

## Testing

- Always test and verify your code!
- catching and fixing bugs earlier is far cheaper than doing so later
- test-driven development:
    * write a test that fails, implement code to make the test pass
    * rinse and repeat

### Test Types

- unit tests:
    * the person coding writes these
    * need to be small and execute fast
    * run these tests every time your code changes
- acceptance tests:
    * test your code against predetermined specifications
      (these may be your customer's specifications or needs)
    * may constitute a demo in front of an audience or something
      programmatic
- regression tests:
    * similar to unit tests
    * involve greater chunks of your code at a time
    * run these nightly or on some other schedule
- user tests:
    * the intended user testing your code

## How To Test

- should be automatic and easy
- test code needs to be of high quality and clear as well
- every piece of test code should test one thing
- test often
- do [happy path](https://en.wikipedia.org/wiki/Happy_path) testing
- do failure testing as your code needs to fail in an expected manner
- do boundary testing
- unit tests should not show random behavior but higher-level testing
  may do so
- minimize time spent debugging by writing lots of tests

## Improving Code / Refactoring

- pre-requisite for refactoring is automated tests (do not start
  refactoring without these)
- tip: when you want to use or modify someone else's code, write tests for it

## Methodologies

- waterfall:
    * step-by-step implementation of the whole
    * the whole only works once all steps have been implemented
    * finish each step in sequence
- agile:
    * finish a simple version of the whole in a short period of time
    * lean software (few features) initially and add features across
      the entire system so as to keep the whole usable
      (iterative development process)
    * agile methodologies: scrum, kanban, etc.

Here is a recent article on how
[Microsoft switched from a waterfall to an agile approach](http://arstechnica.com/information-technology/2014/08/how-microsoft-dragged-its-development-practices-into-the-21st-century/).

## Human Factor

- writing software is always a team effort
- write your code with the intention of your code becoming common property
  (avoid the 'my code' mentality and do not shy away from modifying
   someone else's code)
- avoid scenarios where just one person understands part of the code

## Other Important Topics Touched Upon

- version control
- code review
- pair programming

## References

- [BA Tate: Seven Languages in Seven Weeks](http://shop.oreilly.com/product/9781934356593.do)
- [Martin Fowler: Refactoring: Improving the Design of Existing Code](http://www.amazon.co.uk/Refactoring-Improving-Design-Existing-Technology/dp/0201485672)
- [Robert C. Martin: Clean Code](http://www.amazon.co.uk/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882)
- [Pete Goodliffe: Code Craft](http://www.amazon.co.uk/Code-Craft-Practice-Writing-Excellent/dp/1593271190)
- [Andrew Hunt, David Thomas: The Pragramatic Programmer](http://www.amazon.co.uk/Pragmatic-Programmer-Andrew-Hunt/dp/020161622X)
- [Steve McConnell: Code Complete](http://www.amazon.co.uk/Code-Complete-Practical-Handbook-Construction/dp/0735619670/)

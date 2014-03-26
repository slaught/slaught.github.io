---
layout: post
title: "rbx dev ui: unified concept, part 2"
description: "musings on a possible unified concept"
category: stream of thought
tags: [hci, rbx, nikita, rubinius]
---
{% include JB/setup %}

## warnings
There is no part 1 yet. It is a longer conversation to get started. So I am
jumping into the part where I am at. Confusion is to be expected.


## Metaphor & Unified Concept
Trying to develop a UI for developers tied in with Rubinius. There are many
ideas, goals, tasks and activities. But there is no Unified Concept nor
Metaphor. While it may be possible to proceed without it, I do not think we
will have useful output without one.

[Brian](http://brixen.github.io) and I had been discussing the Developer UI
for the last couple of months. We have been talking about the missing tools
and what the value of certain concepts are. 

One of them is static type checking. The critical question is static type 
checking required or are there
real alternatives that achieve similar results?  We have 
generate good data and some excellent hypothesises which will be
tested over the next few months. 

## Backtrace 
One of the use cases we are studying is Backtraces. Rubinius has a great back
trace on seg fault or other errors. It needs to be extended to capture the
trace of all running threads. But the core problem is the backtrace is not
actionable. None of them are. If read it you can get an idea of where to look.
But even that is only a general guide. It seldom points to the real problem.
And it doesn't even show the code just a line number.
Why not just show me the code? 

Brian's idea is to take the actual execution values that are visible in the
backtrace and layer them over the source code. Then provide a way to move up
and down the backtrace stack and jump to the specific source code in the call
chain.

## Programming Languages
Programming languages are tools to express solutions inside a problem's
domain. 

## Type Annotation
Haskell has a concept of Type Annotation. By default Haskell uses Type
Inference to figure out the types. But sometimes that doesn't always work.
Sometimes it works just fine but you want to make sure it will always work.
These leads to Type Annotation or user specified type information. 

## Literate Programming

> [Literate programming](http://www-cs-faculty.stanford.edu/~uno/lp.html) is 
> a methodology that combines a programming language
> with a documentation language, thereby making programs more robust, more
> portable, more easily maintained, and arguably more fun to write than programs
> that are written only in a high-level language. The main idea is to treat a
> program as a piece of literature, addressed to human beings rather than to a
> computer. The program is also viewed as a hypertext document, rather like the
> World Wide Web. -- Donald E. Knuth

[Nuweb](http://nuweb.sourceforge.net/) works with any programming language and LaTeX.

## Embeddable Languages
Embeddedable SQL. Embeddable Anything in Anything. Rdoc/Yard are embedded
languages.

## Why Binary?
IDEs seems to store extra information in binary form
to be integrated into the UI. Smalltalk is the most extreme example. The
Smalltalk VM is the system, code and UI all in one. 

## Similar 
* [Acme: A User Interface for Programmers](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.169.4065)
* [The Oberon System](http://dl.acm.org/citation.cfm?id=79483.79487)
* [The Oberon System](http://dl.acm.org/citation.cfm?id=102909)
* [A structural view of the Cedar programming environment](http://dl.acm.org/citation.cfm?id=6465.6466)
* [Eclipse](https://www.eclipse.org/)


# now what?
Reading [Niklaus Wirth's
ideas](http://dl.acm.org/citation.cfm?id=1110638.1110671) on languages and
computing in general over the last several decades is telling. 

I have been thinking alot about [Plan 9](http://plan9.bell-labs.com/plan9/)
recently. It was [released under the
GPL](http://akaros.cs.berkeley.edu/files/Plan9License) on Feb 8, 2014. [Fork
it!](https://github.com/brho/plan9) 

I used plan9 way back when for a while. It didn't work on all the hardware that I
wanted to use at the time so I backed away and accepted lesser tools. I look
at my compute systems now and I wonder what could have been.

The unifing concept is __Text__. 

The problems are encoding as much as possible into the source code as text.
_nuweb_ and _Literate Programming_ show a path forward. Wirth notes that the
language specification is critical to having a working langauge. The parser
tools are not important but building parsers (plural) is necessary. The
visualization of the multilayers of data is important. Encoding of then information 
into the source code as text is important. Or at least expressing the data as
manipulatable text.

To be continued.





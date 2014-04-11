---
layout: post
title: "rbx dev ui unified concept part 1"
description: "musings on a possible unified concept"
category: stream of thought
tags: [hci, rbx, nikita, rubinius]
---
{% include JB/setup %}


###### note 
This is part 1. You can 
[read Part 2]({{ site.url }}/stream%20of%20thought/2014/03/26/rbx-dev-ui-unified-concept-part-2/).

## Prehistory
I have been struggling with how to tell this story. There are several
competing things which I want to do. I want to talk about the current thinking
on the topic, I want to talk about how the current thinking was arrived at, I
want to talk about my influences, I want to reference @brixen's own story on
this topic and I want to talk about an interesting research question underlying
everything. 

This is a bit too much to write about. I also only wish to speak for myself.

## Evolution of Rubinius

> Rubinius is a modern implementation of the Ruby language.
> Rubinius is designed for concurrency, using native threads 
> to run Ruby code in
> parallel on all CPU cores. It provides a bytecode virtual machine, a precise,
> low-pause generational garbage collector, and an LLVM-based 
> native machine code
> JIT compiler. The Ruby core library and Rubinius tools are written in Ruby,
> making a smaller, consistent system that is easier for Ruby programmers to
> understand and modify. Rubinius includes a C-API interface for compatibility
> with C-extension libraries and gems written for MRI/CRuby. 
> Rubinius created and
> maintains RubySpec, which provides an executable specification of the Ruby
> programming language.


## Scaling Ruby
Much like [Go](http://golang.org), Rubinius is trying to be a modern
concurrent, scalable language implementation.

Scalablity can mean many things. 
: code scaling across multicore CPUs
: code scaling multiple machines
: teams scaling development of a large codebase 
: products scaling to large number of customers 

Many companies have Ruby codebases they have rewritten in other languages
because MRI is slow and not concurrent, MRI is unwieldy and 
there are issues with large code bases and dynamic languages in general. 

I scaled Enova's legacy Ruby 1.8.7 app to millions of customers 
and hundreds of millions of dollars. I did it with hardware and tweaking all
the support systems around the Ruby code base. We did fix some of the obvious
flaws in the code and in MRI but there were limits. Switching to Rubinius will
half the necessary hardware for the app. This is easily several million
dollars in savings and reduced future spending.

Most companies don't have me working for them so the only option is to
rewrite. 

## Plans for Tools
There is a series of tools which need to be developed. The first is a Ruby
language migration tool. The migration tool will identify areas in your code
bases which need to be changed to run the code in a different version of the
language. Moving from Ruby 1.8.7 to Ruby 2.0 would identify
syntax and semantic problems and highlight the parts of the code which must be
changed. The second tool is a method to quantify the quality of a testsuite.
The main concept is to measure how well a test suite is working beyond just
simply coverage. The questions to be answered are like 'how many tests are
covering a particular area', 'how much redundancy is in the tests', 'are the
tests organized and grouped effectively'. The third tool is a code database.
The database has all the information that the interpretor generates about a
program. The database can also store performance statistics. This provides a
base on which to build other tools. The fourth tool is a ruby source code
pretty printer similar to _go fmt_.

## Tying into Developer Workflow
With these new tools, the questions naturally arise of how and when 
to use them. How can these tools fit together and be used
by developers in their everyday work? A collection of command line programs is
the obvious answer. But it also means developers will have to spend time on
discovery and figuring out how the tools work together themselves. This is the
way of the weak. I want to find a way to integrate these tools into a seamless
system. I want these tools to have a defined part in the workflow of most
developers. I want a nice visualization of the codes runtime statistics and a
representation of what it is doing that is useful to the developer. This is
the way of hubris and the stupid. :)


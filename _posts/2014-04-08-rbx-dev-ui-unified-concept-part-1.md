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
this topic and I want to talk about an interesting research qustion underlying
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
: code scaling mulitple machines
: teams scaling development of a large codebase 
: products scaling to large number of customers 

Many companies have Ruby codebases they have rewritten in other languages
because MRI is slow and not concurrent, MRI is unweidling and 
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


## Tying into Developer Workflow






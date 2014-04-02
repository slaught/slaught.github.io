---
layout: post
title: "ruby require fix"
description: ""
category: 
tags: ["rbx","idea"]
---
{% include JB/setup %}


## Rubinius and _mmap_

I had an idea a few weeks ago. Use _mmap_ for mapping all source files into
the processes memory and allow the OS to manage the file buffering. Right now
Rubinius use standard C++ iostreams to read in the files. The advantage of
this is fast access and continued access to the code. A 64-bit process would
be ideal but even in a legacy app with 50,000 files and 200 mb of source code
it can fit into a 32-bit process space. The legacy app I worked with used a
process memory of only 300 mb of heap. All in it is less than 
30 bits of process space needed.

Most programs won't even come close to that. Of course Rubinius has
MachineCode and CompiledCode data along with the source so that ups the
numbers. But worst case is double the space needed to 31 bits. of course even
if it needs all 32 bits or goes over for apps this large you should be using
64-bit anyways.


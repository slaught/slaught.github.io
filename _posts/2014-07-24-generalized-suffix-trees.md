---
layout: post
title: "Generalized Suffix Trees"
description: "research into generalized suffix trees"
category: research
tags: []
---
{% include JB/setup %}

# Generalized Suffix Trees


### A Problem 
I was researching a problem last week. I was trying to figure out the minimium
number of elements from a list of sets of elements would uniquly identify the set to
which the elements belong. The sets are unique in total but may have subsets
of elements in common. I'd also like to know what the probablity for a given
number of elements to uniquely select the set.

The practical application is I have small subset of elements and if I can
identify the set they belong to I can determine the other elements which will
help me preform a more accurate activity. The probablity is to help make a
better choice if there are several sets selected. 

I fell down the rabbit hole. I found some machine learning algos to guess but
I wanted an exact answer. After some more research I realized I really have a
substring that I am trying to match against a list of stings. My problem can
be restated as the length of the Longest Common Substring of the list of
Strings plus 1. In my first round I checked the "Longest common subsequence".
I dismissed it as the subsequence is not what I am looking for. After trying
to explain my problem to some other people is when I realized I had a
substring problem. The elements are not characters but numbers. But they can
be mapped to characters and the sets can be mapped to strings. So found the
underlying problem. 

### A solution

One solution to find the longest common substring of a set of strings is to
build a generalized suffix tree. A suffix tree is a trie data structure
allowing the storage of all substrings of a given string in linear space. The
exact definition is below. A suffix tree holds one strings. The generalized
suffix tree holds a set of strings. To find the longest common substring you
search for the deepest internal node which has a leaf node from all the strings 
in the set in the subtree below. 



#### Suffix Tree Definition ####

  * A suffix tree ST for an m-character string S is a rooted directed tree with exactly m leaves numbered 1 to m.
  * Each internal node, other than the root, has at least two children and each edge is labeled with a nonempty substring of S.
  * A suffix tree ST for an m-character string S is a rooted directed tree with exactly m leaves numbered 1 to m.
  * Each internal node, other than the root, has at least two children and each edge is labeled with a nonempty substring of S.



## References ##

* [Wikipedia Longest Common Substring Problem](http://en.wikipedia.org/wiki/Longest_common_substring_problem)
* <https://www.cs.cmu.edu/~ckingsf/bioinfo-lectures/suffixtrees.pdf>
* <http://www.cs.uku.fi/~kilpelai/BSA05/lectures/slides08.pdf>
* <http://www.cs.ucf.edu/~shzhang/Combio11/lec3.pdf>
* [Github: Java Generalized Suffix Tree](https://github.com/abahgat/suffixtree)
* [Suffix Trees and Suffix Arrays](http://www.cs.ucf.edu/~shzhang/Combio/suffix.pdf)
* <http://acm.mipt.ru/twiki/bin/view/Ruby/SuffixTree>
* <http://en.wikipedia.org/wiki/Suffix_tree> 
* [DrDobbs: A Practical Suffix-Tree Implementation for String Searches](http://www.drdobbs.com/database/a-practical-suffix-tree-implementation/184404184)
* [DrDobbs: Algorithm Alley: Fast String Searching with Suffix Trees](http://www.drdobbs.com/database/algorithm-alley-fast-string-searching-wi/184409945)

### Releted References ###
* [Develop high performance string data structures](http://www.naskitis.com/)
* [Engineering scalable, cache and space efficient tries for strings](http://dl.acm.org/citation.cfm?id=1873121)
* [Efficient and Practical Non-Blocking Data Structures](http://www.cse.chalmers.se/~tsigas/papers/Haakan-Thesis.pdf)
* [Redesigning the string hash table, burst trie, and BST to exploit cache](http://dl.acm.org/citation.cfm?id=1671970.1921704)
*




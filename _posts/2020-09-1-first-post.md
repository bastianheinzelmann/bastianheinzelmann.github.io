---
layout: post
title: "Endless 2D-Maps with WFC: Part 1"
date: 2021-1-21
description: This is just a random test post
tags: 
 - WFC
 - Wave Function Collapse
 - Unity
 - 2D
 - Procedural Generation
share: true
commentsId: '1'
---

# 1. Get Wave Function Collapse to run

In my first blog post I will show my implementation of Maxim Gumin's Wave Function Collapse algorithm, short WFC. WFC derives rules from an existing tilemap and generates a new tilemap based on them. It is a pretty neat algorithm and I will try to generate endless worlds with it.

So I decided to go with Unity for this project, simply because it has the best support for 2D-Games. It also has it's own tilemap class, which I am not entirely sure is worth using, though. 

### Goals

The goal for this post is to create script, that will derive rules from a tilemap a human made and save them in a smart way. Then we will look how to implement the actual algorithm. 

### Let's make some rules

One of the advantages of WFC is, that we can create our own little tilemap and the algorithm will create something similar, so we can influence the outcome to a certain degree. But that means we have more work to do and let the user create a tilemap from which a script needs to derive rules. In this case I decided to write a C# editor script, that generates rules from a selected ```Tilemap```  and stores them in a ```Scriptable Object```.  
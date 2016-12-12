---
layout: post
title:  "Graph Traversal: A Primer"
date:   2016-12-11 13:55:28 -0500
categories: jekyll update
---

## What we talk about when we talk about graphs

* Trees: no cycles
* Directed graphs: each edge has a direction
* Undirected graphs: edges don't have a direction (there is an edge from A to B iff there is an edge from B to A)

## What makes a graph?

* Edges
* Vertices

## What is graph traversal?

Graph traversal, or graph search, is the process of going through each vertex and gathering information about it.

## What can we learn from graph traversal?

 * Shortest paths
 * Connectedness
 * Whether a graph is a tree

## Traversal algorithms
![Example graph](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f7/Binary_tree.svg/220px-Binary_tree.svg.png)

### Depth-first search
Visits children before siblings. That is, explores the full depth of a path before traversing the breadth.

The algorithm is as follows:

- Choose a root node
- From that node, go to an unvisited child node
- When there are no longer any unvisited child nodes, traverse back until you find one
- Repeat until all nodes are visited

In graph above:

* 2 as root.
* Next visit 7.
* Next visit 2.
* No more unvisited children, backtrack to 7.
* Next visit 6.
* Next visit 5.
* Backtrack to 6.
* Next visit 11.
* Backtrack to 6.
* Backtrack to 7.
* Backtrack to 2.
* Next visit 5.
* Next visit 9.
* Next visit 4.

Good for:

* Solving mazes
* [Topological sorting](https://en.wikipedia.org/wiki/Topological_sorting)

### Breadth-first search
Visits siblings before children. That is, explores the full breadth of a graph before going to the next level. Uses a queue.

The algorithm is as follows:

- Choose a root node
- From that node, enqueue all unvisited children
- Visit each item in the queue and enqueue their unvisited children
- Repeat until all nodes are visited

In graph above:

* 2 as root.
* Enqueue 7 and 5. Queue: [7, 5]
* Visit 7, enqueue its children, 2 and 6. Queue: [5, 2, 6]
* Visit 5, enqueue its child, 9. Queue: [2, 6, 9]
* Visit 2, it has no children. Queue: [6, 9]
* Visit 6, enqueue its children, 5 and 11. Queue: [9, 5, 11]
* Visit 9, enqueue its child, 4. Queue: [5, 11, 4]
* Visit 5, it has no children. Queue: [11, 4]
* Visit 11, it has no children. Queue: [4]
* Visit 4, it has no children. Queue: []

Good for:

* Finding shortest paths (by number of edges)
* Serialization/Deserialization of binary trees

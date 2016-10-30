---
layout: post
title: Unlimited networks (II)
---

We can edit the `nt` function to make graphs and compuate nodes and netowrk properties. 

First, let's load `igraph`, a graph package in R.

    library(igraph)
    
We can make graphs within the `nt` function from adjacency matrix

    nt <- function(d) {
    DM <- dist[] < d
    diag(DM) = 0
    g <- graph.adjacency(DM) #generate a graph
    return(DM)
    }
    
    

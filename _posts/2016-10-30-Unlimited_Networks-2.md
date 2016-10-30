---
layout: post
title: Unlimited networks (II)
---

We can edit the `nt` function to make graphs and compuate nodes and netowrk properties. 

First, let's load `igraph`, a graph package in R.

    library(igraph)
    
Now we can make graphs from adjacency matrices within `nt`.

    nt <- function(d) {
    DM <- dist[] < d
    diag(DM) = 0
    g <- graph.adjacency(DM)
    return(DM)
    }
    
    

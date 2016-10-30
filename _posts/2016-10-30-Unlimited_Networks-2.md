---
layout: post
title: Unlimited networks (II)
---

We can edit the `nt` function to make graphs and compuate nodes and netowrk properties. 

First, let's load `igraph`, a graph package in R.

    library(igraph)
    
Now we can make graphs from transforming adjacency matrices within `nt` and find node centralities.

    nt <- function(d) {
    DM <- dist[] < d
    diag(DM) = 0
    g <- graph.adjacency(DM)
    btwn <- betweenness(g, directed = FALSE)
    close <- closeness(g, mode = "out")
    degree <- degree(g)
    return(list(betweenness.centralities = btwn, closeness.centralities = close, degree.centralities = degree))
    }

Now you have a basic yet useful function to generate many networks and find node properties in those networks!!  [Learn mode](https://hhsieh.github.io/Unlimited_Networks-3/)

    

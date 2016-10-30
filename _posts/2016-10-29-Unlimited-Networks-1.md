---
layout: post
title: Unlimited networks (I)
---

Suppose you have 100 nodes; each of them has its own x and y spatial coordinates in kilometers. You are interested in learning how the structure of the network composed of the nodes and the edges forming between them affects the system dynamics.  Unfortunately, you have no clue whether there is an edge between any two nodes and, therefore, cannot conclude the configuration of the spatial network.  What should you do to generate testable networks in order to answer the interesting question you have in mind?

![_config.yml]({{site.baseurl}}/images/hundred_nodes.jpeg)

An intuitive solution is, based on knowledge you have about the system, to decide whether there is an edge between two nodes.  Let say, nodes between which the distance is smaller than _d_ kilometers are connected. Otherwise, they are not. 

In R, we can easily reproduce the nodes data as below.

    set.seed(5)
    x = rnorm(100) * 100
    y = rnorm(100) * 100
    data = data.frame(x, y)
    
A distance matrix can help us generate networks in the following steps.

    dist <- as.matrix(dist(data))
    
```{r, echo = FALSE}
dist(head)
```
    
This is a realistic question - it's a hurdle to jump over given the ecological data I have to deal with. And, in fact, the scale in space-time continuum of my question is much greater than the example above!

It is fortunately easy in math, in this circumstance, to generate hypothetical networks.  The power of modern-day computers also makes it easy to instantly generate as many networks as one wishes.

The magic is the fundamental matrix of Markov Chain, which works in any circumstance in which network structures were 


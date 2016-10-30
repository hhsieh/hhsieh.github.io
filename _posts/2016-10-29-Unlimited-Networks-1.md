---
layout: post
title: Unlimited networks (I)
---

Suppose you have 100 nodes; each of them has its own x and y spatial coordinates in kilometers. You are interested in learning how the structure of the network composed of the nodes and the edges forming between them affects the system dynamics.  Unfortunately, you have no clue whether there is an edge between any two nodes and, therefore, cannot conclude the configuration of the spatial network.  What should you do to generate testable/hypothetical networks in order to answer the interesting question you have in mind?

![_config.yml]({{site.baseurl}}/images/hundred_nodes.jpeg)

An intuitive solution is, based on the knowledge you have about the system, deciding whether there is an edge between two nodes.  Let say, nodes between which the distance is smaller than _d_ kilometers are connected. Otherwise, they are not. 

In R, we can easily reproduce the nodes data as below.

    set.seed(5)
    x = rnorm(100) * 100
    y = rnorm(100) * 100
    data = data.frame(x, y)
    
A distance matrix can help us generate networks in the following steps.

    dist <- as.matrix(dist(data))

Now, let's set up _d = 20_. Two nodes of which distance smaller than _d_ is connected.

    DM <- dist[] < 20
    diag(DM) = 0

In this way, we create an adjacent matrix of the network. Isn't it easy?

This is a great first step. To solve our problem, we need more. [See the next post.](http://hhsieh.github.com/Unlimited-Networks-II)


    
    
    

    



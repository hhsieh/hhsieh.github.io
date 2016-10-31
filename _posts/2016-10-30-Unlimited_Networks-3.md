---
layout: post
title: Unlimited networks (III)
---

Now it comes a bigger problem. Due to budget constraint, you only have sampled all of the nodes within a rectangular plot.  That comes up with the total 100 nodes you have as in [Unlimited-Networks (I)](https://hhsieh.github.io/Unlimited-Networks-1/).

This constraint suggests that we do not have an entire network -- there would be more nodes outside the plot of which data we are unable to obtain. This is unfortunate as an incomplete network would just affect concerned analyses. To solve this problem, one may think to hypothetically generate nodes outside the plot, perhaps based on the spatial pattern of the nodes inside the plot. Here, nevertheless, I am going to propose an alternative solution. We will simply use the information have in hand to approach the reality. 

Let's say the spatial coordinates of the four corners of the plot are, respectively, (-240, -270), (240, -270), (-240, 270), (240, 270).

There would be some nodes located within distance _d_ to one of the four rectangular plot boundaries.  [Insert visualization](https://hhsieh.github.com/16-10-30-figure-1)  If this is the case, the nodes themselves and the nodes they share the same compartments with should be removed as they potentially are connected to the _unknown nodes_ outside the plot. 

To deal with this issue, we can write another function. I will apply the fundamental matrix of Markov Chain as it works really fast and accurately generates compartments within networks. 


    nt_inv <- function(d) {
        DM <- dist[] < d
        diag(DM) = 0
        I <- diag(1, nrow=nrow(dist), ncol=ncol(dist))
        D <- sapply(1:nrow(dist), function(z) DM[,z]/(z+1)) 
        inv <- solve(I-D)
        return(inv)
        }
    

---
layout: post
title: Unlimited networks (IV)
---

Now we need to do something a little bit more challenging. It is not too bad, however. The idea is really logical and may even come intuitively.

What we need to do is to use the four boundray values of the plot - the minimal x-coordinate, the maximal x-coordinate, the minimal y-coordinate and the maximal y-coordiate, to delete the nodes within the distance to plot margins and also delete the nodes that these nodes sharing the same compartments with.


    rec <- function(d, xmin, xmax, ymin, ymax) {
        ....
    }

Now the new functions have 5 parameters. We will need to insert more things into it.

    rec <- function(d, xmin, xmax, ymin, ymax) {
        DM <- dist[] < d
        diag(DM) = 0
        I <- diag(1, nrow=nrow(dist), ncol=ncol(dist))
        D <- sapply(1:nrow(dist), function(z) DM[,z]/(z+1)) 
        inv <- solve(I-D)
        cmtsize <- function(x) length(which(inv[,x]!=0)) #compartment sizes of nodes
        comp <- function(x) which(inv[,x]!=0)[1] #compartment identities
        return(list(compartment_size = cmtsize, compartment_id = comp))
    }


within this function, `compartment_size` reports the compartment size of the compartment each node belongs to. `compartment_id` reports the identity of each compartment that each node belongs to.



    




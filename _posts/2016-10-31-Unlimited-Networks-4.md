---
layout: post
title: Unlimited networks (IV)
---

Now we need to do something a little bit more challenging. It is not too bad, however. The process is really logical and may even come intuitively.

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
        # remove nodes within <d to plot boundaries
        
    
    }



    




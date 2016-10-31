---
layout: post
title: Unlimited networks (IV)
---

Now we need to do something a little bit more challenging. It is not too bad, however. The idea is really logical and may even come intuitively.

What we need to do is to use the four boundary values of the plot - the minimal x-coordinate, the maximal x-coordinate, the minimal y-coordinate and the maximal y-coordiate, to delete the nodes within the distance to plot margins and also delete the nodes that these nodes sharing the same compartments with.


    rec <- function(d, xmin, xmax, ymin, ymax) {
        ....
    }

Now the new functions have 5 parameters. However, we will do it step by step. The following function does not incorporate values of plot boundaries yet, but it tells us which nodes belong to which compartments.

    rec <- function(d) {
        DM <- dist[] < d
        diag(DM) = 0
        I <- diag(1, nrow=nrow(dist), ncol=ncol(dist))
        D <- sapply(1:nrow(dist), function(z) DM[,z]/(z+1)) 
        inv <- solve(I-D)
        
        x_cord <- function(x) data$x[x] #x-coordinates of nodes
        y_cord <- function(x) data$y[x] #y-coordinates of nodes
        cmtsize <- function(x) length(which(inv[,x]!=0)) #compartment sizes of nodes
        comp <- function(x) which(inv[,x]!=0)[1] #compartment identities
        
        node_prop <- list()
  
        N <- nrow(dist)
        for (i in 1:N) {
          node_prop[[i]] = data.frame(x_cord = x_cord(i), y_cord = y_cord(i), compartment_id = comp(i), compartment_size = cmtsize(i)
            )
          }
  
        nodeproperties <- do.call(rbind, node_prop)
        return(nodeproperties)
        }


Within this function, `compartment_size` reports the compartment size of the compartment each node belongs to. `compartment_id` reports the identity of each compartment that each node belongs to.

We will use the results of `rec` to improve this function itself by deleting undesired nodes.



**(Unfinished)**



    




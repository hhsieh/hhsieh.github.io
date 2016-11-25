---
layout: post
title: Calling a function for multiple times in Python (II)
---

Certainly, you can find more than one way to run a function for multiple times to perform a task in Python (and other languages).  Here I am just going to use the same approach as in [Calling a function for multiple times in Python (I)] (https://hhsieh.github.io/calling-function-multiple-times/).

The question goes:

You have a series of numbers: 3, 4, 5, 7, 9, 12, 15... What will be the Nth number (N >= 1)?

Carefully looking at the series of numbers, you may find it increases in the pattern 1, 1, 2, 2, 3, 3, ...., in each step. we can write a function to reflect the pattern and find the value of the Nth number.

    def series(N):
        if N % 2 == 0:
            print 3 + (1 + N / 2) * (N / 2) - (N /2)
        else:
            print 3 + (1 + N / 2) * (N / 2)
        
No, assume we need to find the 48th number. We simply do 

    seris(48)
    
It will give us `579`

We can ask for values of a sequence, for instance, from 60th to 84th.

    for N in range(60, 85):
        series(N)
        
It gives us:
    
    903
    933
    964
    995
    1027
    1059
    1092
    1125
    1159
    1193
    1228
    1263
    1299
    1335
    1372
    1409
    1447
    1485
    1524
    1563
    1603
    1643
    1684
    1725
    1767

    
    


---
layout: post
title: Calling a function for multiple times in Python
---

Today I am going to blog a little about Python, a language that I have found very helpful in producing clean and productive code.

I will start with "calling a function for multiple time" - We will need a function. I call this function `intersect`. 

The code below suggests this - I have the user input integer, `c`.  I repeat the function `intersect` for multiple times until I finish running through the values from `0` all the way to `c-1` (the so called range in Python).  In total, this will be `c` times.

    c = int(input())
    
    for _ in range(c):
        intersect()
        
And `intersect` is function that I would like to repeat.  This is a function that prints "YES" if two strings share at least one substring and print "NO" if they share no substring at all.

    def intersect():
        a = map(str, raw_input())
        b = map(str, raw_input())
        d = set(a).intersection(b)
        if len(d) > 0:
            print "YES"
        else:
            print "NO"

Now, let's try it out. 

    c = int(input())

Try c = 2

    for _ in range(c):
        intersect()

You will find that it asks to enter two strings. Give it the two strings. It will pop up "YES" or "NO", depending on whether the two strings share any substring(s). The process will repeat `c` times as defined. 

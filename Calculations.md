# Calculating with AlaSQL

All calculations with numbers within the default in-memory database of AlaSQL uses the Javascript engine.

Unlike many other programming languages, JavaScript does not define different types of numbers, like integers, short, long, and floating-point.  JavaScript numbers are always stored as double precision floating point numbers.

To people familiar with calculation challenges in javascript it will not come as a surprise, but without setting a different backend AlaSQL can give the following (unexpected) output:

    SELECT 0.2 + 0.1
    -> [ { '0.2 + 0.1': 0.30000000000000004 } ] 

As [The floating point guide](http://floating-point-gui.de/) states:

> **What can I do to avoid this problem?**
> 
> That depends on what kind of calculations you’re doing.
> 
> * If you really need your results to add up exactly, especially when you work with money: use a special decimal datatype.

> * If you just don’t want to see all those extra decimal places: simply format your result rounded to a fixed number of decimal places when displaying it.

> * If you have no decimal datatype available, an alternative is to work with integers, e.g. do money calculations entirely in cents. But this is more work and has some drawbacks.


You can see more about the pitfalls of floating points at 
http://mortoray.com/2015/07/06/essential-facts-about-floating-point-calculations/
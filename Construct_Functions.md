Consider the example that we come across during the lecture:
```r
make.power <- function(n) {
  pow <- function(x)
  {
    x^n  
  } 
  pow 
}

cube <- make.power(3)
square <- make.power(2)
```
_Question: How does the function compute the values of cube and square?_

----

Let's try if breaking down these codes helps. Pay attention to the outer part first:
```r
make.power <- function(n) {
  pow <- function(x)
#   {
#     x^n  
#   } 
  pow 
}
```

So basically make.power is a function, which takes n as the input argument, creates another function called pow, and finally prints out pow. Note that n is still unused so far.

It seems like that pow is what matters. Let's take a look at pow.
```r
# make.power <- function(n) {
  pow <- function(x)
  {
    x^n  
  } 
#   pow 
# }
```

Now we know that pow is a function, which takes x as the input argument, and calculates x^n. Note that the n is used here.

Thus, let's take cube for clarification:
```r
cube <- make.power(3)
# What really heppens is like:
pow <- function(x) {
  x^3
}
cube <- pow
```
Thus, cube is pow now, and cube is a function as well.
```r
cube(3)
# What really heppens is like:
# pow(3)
3^3
```

The answer is 27.

Further discussions are welcome. :)

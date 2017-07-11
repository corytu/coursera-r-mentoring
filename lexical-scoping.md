Given a sudo code below:

```r
v1 = 5
f <- function(a){
  g <- function (b){
    v1 <- v1^2
  }
  a <- a + v1
}
```
_Question: Will function f use v1 = 5 or v1 = 25 to compute a = a + v1?_

----

Let me revise the sudo code a little bit:

```r
v1 = 5
f <- function(a){
  g <- function (b){
    v1 <- v1^2
    v1  # Make g return the value
  }
  print(g())  # Print out the result of g()
  a + v1  # Make f return the value
}
```

Now if you type f(1), you'll get 25 and 6.

This is the idea of lexical scoping: "It looks up symbol values based on how functions were nested __when they were created, not__ how they are nested __when they are called.__"

When you call f, f calls g, g doesn't have v1, so it looks one level up, but f doesn't have v1 either, so g looks one more level up to the global environment, and take v1 as 5. The pretty same thing happens when f calculates a + v1.

However, if I change that code into this one below:

```r
v1 = 5
f <- function(a){
  g <- function (b){
    v1 <<- v1^2  # Note that <- is changed into <<-
    v1
  }
  print(g())
  a + v1
}
```

If you try f(1) again, you'll see 25 and 26 as the answers. The __<<- pushes the assignment of v1 one level up__ to its parent environment, which is f. As a result, f does have v1 when it computes a + v1, and f will use that instead of seeking it in its parent environment.

---

_Challenge: What will be returned when `f(3)` is executed? (DON'T run it in R console. Reason out your answer!)_

```r
f <- function(x) {
  g <- function(y) {
    y + z
  }
  z <- 4
  x + g(x)
}

z <- 10
f(3)
```

Hint: You probably need the concepts of [constructor functions](constructor-functions.md).
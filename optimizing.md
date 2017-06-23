[Construction function questions](https://www.coursera.org/learn/r-programming/discussions/weeks/2/threads/0YK_wlcBEeeMcg4GWtvWkg)

_Questions:_

```r
make.NegLogLik <- function(data, fixed=c(FALSE,FALSE)) {
  params <- fixed
  function(p) {
    params[!fixed] <- p
    mu <- params[1]
    sigma <- params[2]
    a <- -0.5*length(data)*log(2*pi*sigma^2)
    b <- -0.5*sum((data-mu)^2) / (sigma^2)
    -(a + b)
  }
}
```

1. After params <- fixed, is params a list with two "FALSE"s in it?
2. function(p), what is the parameter p? And in the following statement params[!fixed] <- p, does this assign p to params[TRUE, TRUE]? Again, what is p? When the function was called like this: `nLL <- make.NegLogLik(normals, c(FALSE, 2))`, what will params[!fixed] <- p do? Assign p to params[TRUE, !2]?
3. What value is mu? Should params[1] not equal "FALSE"?

---

I would answer some of them, so that you can try to test and play with R in order to figure out the rest.

1. By default, after params <- fixed, params is a __vector__ with two "FALSE"s, not a list.
2. p is another argument which is not yet specified after you call `make.NegLogLik`. In fact, `make.NegLogLik` returns a __function__ with an argument p (nLL in the lecture) to be optimized.
3. The statement params[!fixed] <- p assigns p to where fixed is FALSE (those are not supposed to be fixed would be replaced with p).
You have to be very familiar with subsetting in R (Week 1 lecture) to understand this problem. Figure:

```r
fixed <- c(FALSE,FALSE)
params <- fixed
params[!fixed]
# This returns two FALSEs. Why?
# How about:
x <- 1:2
x[!fixed]
# What do you see? Why is that?

# What if:
fixed <- c(FALSE, TRUE)
params <- fixed
params[!fixed]
params[!fixed] <- 10
# Which of params is substituted with 10?
# Where does the 1 come from?
# Hint: Try as.numeric(TRUE), and review the coercion concepts.

# And what if:
fixed <- c(FALSE, 20)
params <- fixed
params[!fixed]
# What does !fixed return here? Why?
# Hint: Try as.logical(20)
```

You need the curiosity to figure all these questions. Cheers!!

Yu-Zhen

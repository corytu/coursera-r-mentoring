```r
test <- matrix(6, 2, 3)
apply(test, 1, sum)
# 18 18
apply(test, 2, sum)
# 12 12 12
apply(test, c(1, 2), sum)
# test matrix itself
```

_Question: Why does `apply(test, c(1, 2), sum)` returns the same matrix "test"?_

---

The help document reads that "c(1, 2) indicates rows and columns" for the MARGIN argument. However this sentence may be misleading. I had thought that it would return a list which comprise two elements, where the first one is c(18, 18) and the other is c(12, 12, 12). I was wrong.

In fact, __c(1, 2) here applies the function to every element of the matrix__. One can try `apply(test, c(1,2), function(x) x^2)`, which is a concrete example showing the mechanism.
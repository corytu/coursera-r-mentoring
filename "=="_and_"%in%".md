Consider this example:

```r
x <- rep(1:5, times = 2)

x == 1:3
# TRUE  TRUE  TRUE FALSE FALSE FALSE FALSE FALSE FALSE FALSE
# With warnings

x %in% 1:3
# TRUE  TRUE  TRUE FALSE FALSE  TRUE  TRUE  TRUE FALSE FALSE
```

_Question: Why does the results differ from each other?_

---

People need to compare values across objects every now and then. In this case, let's say we want to find out which ones of `x` is 1, 2, or 3. Intuitively, we will do `x == 1:3`, but it is WRONG. Only the first three elements return TRUE even though we know that there is another set of 1:3. (Of course you can do `x == 1 | x == 2 | x == 3` but imagine when you have many values to be compared with...)

The reason for that unexpected output is the vectorization characteristic of R. When we do `x == 1:3`, R does the following things:
* Is x[1:3] == 1:3 respectively? (TRUE TRUE TRUE)
* Is x[4:6] == 1:3 respectively? (FALSE FALSE FALSE)
* Is x[7:9] == 1:3 respectively? (FALSE FALSE FALSE)
* Is x[10:12] == 1:3? (All FALSE but there's no x[11] and x[12] => warnings)

Alternatively we can do `x %in% 1:3` because it checks every single element of `x` to find whether the element is within 1:3.

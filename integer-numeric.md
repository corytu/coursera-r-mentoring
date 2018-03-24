```r
x <- c(1, 2, 3)
class(x)
# "numeric"
y <- 1:3
class(y)
# "integer"
```

_Question: Why x and y have different classes, and what `c` has to do with it?_

----

As you can see, the respective numbers 1, 2, and 3 are not really treated as integers in R, although we human think they are. In fact, 1 could be stored as 1.0000000000000000001 in R.

```r
class(1)
# "numeric"
class(1L)
# "integer"
```

This allows users do various manipulation to the numbers later, while the cost is that float numbers take slightly more resources in memory than integers do. For instance,

```r
format(1, nsmall = 5)
# "1.00000"
format(1L, nsmall = 5)
# "1"
```

You see 1L cannot have digits after the decimal point.

Still, when you run something like `1:3` (or even `c(1:3, 9:12)`), R clearly knows that it is a sequence with integers. To save the memory, they are then saved as integers.

Don't worry about it too much. R is relatively easier in terms of object classes. Just so that you know, in Python 2,

```python
5/2
# 2
float(5)/2
# 2.5
```

You see 5/2 returns 2 because both 5 and 2 are saved as integers by default, and the result would then also have to be an integer. Luckily this doesn't happen anymore in Python 3.

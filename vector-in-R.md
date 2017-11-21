"Vectors" in R doesn't have mathematical sense. Here we have a question from a learner on Coursera:

```r
x <- 1:3
x
# [1] 1 2 3

# Transpose it
t(x)
#      [,1] [,2] [,3]
# [1,]    1    2    3

# Transpose it again
t(t(x))
#      [,1]
# [1,]    1
# [2,]    2
# [3,]    3

# Make calculations
x * t(x)
#      [,1] [,2] [,3]
# [1,]    1    4    9
```

_Question:_<br>
1. Is x a "mathematical" vector?
2. If not, why `t(x)` worked?
3. Why `x * t(x)` showed a weird result?

----

Indeed, "vectors" in R cannot be considered mathematically. Instead, "vectors" here simply means "a series of data _without_ dimensions". Since vectors don't have dimensions, nothing like "row vector" or "column vector" would be discussed, nor would they have matrix operations.

If you look up the documentation of `t` function, you will know why `t(x)` in your example worked: "When x is a vector, it is treated as a column, i.e., the result is a 1-row matrix." Besides, the operations in R is "vectorized operations", which is very unique. (Please go review the lecture of ["Vectorized Operations"](https://www.coursera.org/learn/r-programming/lecture/nobfZ/vectorized-operations) if you are not familiar with it.) Thus, `x * t(t(x))` is not a matrix operation in math and returns weird results.

That being said, you can still create a "mathematical vector" by creating "a matrix with only one row or one column", although it will be a "matrix" in R.

```r
R_vector <- 1:3
class(R_vector)
# "integer"
# Which means R_vector is an interger vector

col_vector <- matrix(1:3)
class(col_vector)
# "matrix"
# Note that this is NOT a vector in R language

row_vector <- t(col_vector)
# row_vector <- matrix(1:3, nrow = 1)
class(row_vector)
# "matrix"
```

I hope the demonstration above helps you to understand. Feel free to ask if you have further questions. :)

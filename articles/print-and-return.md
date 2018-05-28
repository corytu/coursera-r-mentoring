Here are two functions:

```r
f <- function(a,b) {
  print(a^2)
  print(b^2)
}

y <- function(a,b) {
  a^2
  b^2
}
```

_Question: Why do I get \[1\] 4 \[1\] 16 with `f(2, 4)` but get only \[1\] 16 with `y(2, 4)`, which completely ignoring one of my arguments?_

----

First, keep in mind that:

1. Every line in a function is evaluated.
2. The last expression evaluated is (by default) the returned value. Alternatively one can use `return` to return a specific object from a function.

So let's take a look at the two functions, starting from the second one, which should be easier according to the rules above:

```r
y <- function(a, b) {
  a^2
  b^2  # This is the last expression
}
```

As described earlier, the only returned value should be `b^2`, although `a^2` is also evaluated. Hence `y(2, 4)` returns 16.

Now let's see the other:

```r
f <- function(a, b) {
  print(a^2)
  print(b^2)  # This is still the last expression
}
```

`print` is a function which simply prints out the result of the passed expression as long as it is not causing errors. By just evaluating `print`, it prints. Thus, you see 4 and 16 printed out when you execute `f(2, 4)`.

However, still only 16 is returned by `f`. You can try:

```r
result <- f(2, 4)
result  # 16
```

You'll see 4 and 16 are printed again, but `result` is just 16.

If you really need multiple objects to be returned, usually we will use a list (or a named vector in really simple cases like yours):

```r
# In a list
y_list <- function(a, b) {
  list(a_square = a^2, b_square = b^2)
}

# In a named vector
y_vec <- function(a, b) {
  c(a_square = a^2, b_square = b^2)
}
```

Now you can do `y_list(2, 4)` or `y_vec(2, 4)`, store the returned value, and subset what you need in the following analyses. The advantage of returning multiple values in a list is that those values don't have to be in the same class, which is a nice characteristic of lists.

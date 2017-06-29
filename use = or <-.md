```r
x <- 1:10
y = 1:10
identical(x, y)
# TRUE
```
_Question: The effect of `=` seems equivalent to `<-`. I'm already used to `=`, should I change my habits for R language?_

---

__I prefer `<-`__. Let me tell you my reasons.

1. `<<-`, which looks more like `<-`, is needed when assigning values to the parent environment.<br>
This is probably the most important reason. People will need this functionality sometime. For the demonstration of using `<<-`, please refer to [my lexical scoping article](lexical%20scoping.md).

2. `<-` has higher precedence than `=` does in R syntax.<br>
Why doesn't the final case work in the following lines? The reason is related to the parser of R. [This thread](http://stackoverflow.com/questions/1741820/assignment-operators-in-r-and) on Stack Overflow provides more detailed elaboration. Intuitively, the statement `a <- b = 15` requires `b`, which is likely to be unknown, to be assigned to `a` first. However, given that b may not have a value, R has to process `b = 15` first, which is contradictory to R grammar.
```r
a <- b <- 5
a; b
# 5
# 5

a = b <- 10
a; b
# 10
# 10

a <- b = 15
# Error in a <- b = 15: could not find function "<-<-"
```

3. In most cases of assigning values, `=` is equivalent to `<-`, but `<-` is even more general than `=`.<br>
In the first following case, x exists only in the `sum` function scope, while in the second case, x is also declared in Global Environment. Although we don't often need this kind of declaration. Still, using `=` when passing arguments and `<-` when assigning values, as well as proper indents, can make your codes look more compilable. Consider the examples below:
```r
sum(x = c(5, 8, 7))
# 20
x
# Error: object 'x' not found

sum(x <- c(5, 8, 7))
# 20
x
# 5 8 7
```

To sum up, using `=` or `<-` really depends on your preference. You can surely use `=` all the time, but I have given my personal suggestions.

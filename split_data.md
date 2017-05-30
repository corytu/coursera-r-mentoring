One learner on Coursera asked me the following question because inconsistent results were found:

```r
# First attempt
f <- levels(iris[,5])
sapply(split(iris[,1],f), mean)
# setosa versicolor virginica
# 5.842  5.822      5.866

# Second attempt
sapply(split(iris$Sepal.Length, iris$Species), mean)
# setosa versicolor virginica
# 5.006  5.936      6.588
```

_Question: Why is it different when he use factor levels from `levels`?_

---

Before answering this question, we can confirm that __only the second result is correct__ by `tapply(iris$Sepal.Length, iris$Species, mean)`.

The problem in the first method is that the length of f is only 3, and that length is shorter than iris$Sepal.Length. According to the help document of split function, __"f is recycled as necessary and if the length of x is not a multiple of the length of f a warning is printed,"__ which means when we split iris$Sepal.Length with f, R regards it as:

| Sepal.Length | Species    |
|--------------|------------|
|         5.1  | setosa     |
|         4.9  | versicolor |
|         4.7  | virginica  |
|         4.6  | setosa     |
|         5.0  | versicolor |
|         5.4  | virginica  |

In fact, however, these first six rows above are all setosa. Check it with `head(iris)`. Also, compare the difference between `split(iris$Sepal.Length, iris$Species)` and `split(iris$Sepal.Length, f)`.

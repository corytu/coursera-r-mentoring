```r
num <- rep(1:4, times = 2)

# The following lines return values differently
factor(num)
factor(num, labels = c("a", "b", "c", "d"))
factor(num, levels = c("a", "b", "c", "d"))
```

_Question: What is the difference between levels and labels of a factor variable?_

---

The "levels" argument allows us to change the orders (or the baseline) of the factor. In this case, "1" is the baseline category by default because it's the smallest number among the four ones. Still we can change that by `factor(data, levels = 4:1)`, and now "4" is the baseline category.

Thus, if something exist in the data but don't exist in levels, they will be unrecognizable and R returns NAs.

On the other hand, "labels" labels the factor with another set of character strings, in the same order as levels. It doesn't matter if the labels are completely different with the original data, but one should be careful not to be confused after relabeling:

```r
# 1 is "a"
factor(data, labels = c("a", "b", "c", "d"))
# 4 is "a"
factor(data, levels = 4:1, labels = c("a","b","c","d"))  
```

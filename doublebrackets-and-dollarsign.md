Data frames have several extract operators for subsetting data.

_Question: I found on SO that the `$` operator cannot work with variables that are not static for subsetting . I would like a more in depth answer._

----

`$` is commonly used to subset named lists and data frames. They are ailke except that data frames have a tabular shape. Take the following codes for example:

```r
mtcars$"mpg"    # working
mtcars$mpg      # working
mtcars[["mpg"]] # working
mtcars[[mpg]]   # NOT working

my_list <- list(a = 1:3, b = c(TRUE, FALSE))
my_list$"a"     # working
my_list$a       # working
my_list[["a"]]  # working
my_list[[a]]    # NOT working
```

`[[]]` is an indexing operator which takes numbers (e.g. `my_list[[1]]`) or names of the elements (e.g. `my_list[["a"]]`), but the name must be passed with character strings. On the other hand, `$` doesn't have such limitation. As a result, if you do `mtcars$poll`, R will go find a column named "poll" in `mtcars`, which should be `NULL` (nothing), and that probably triggers errors in later part of your codes. But when you do `holder[[poll]]`, R will read what `poll` is, take the string that returns, and do subsetting.

You can find more details in Len's comprehensive article, [Forms of the Extract Operator in R](https://github.com/lgreski/datasciencectacontent/blob/master/markdown/rprog-extractOperator.md).

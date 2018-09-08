# Coursera R Mentoring
_Mentoring records and my helping articles on Coursera (Last update: September 8, 2018)_

Some questions have been raised frequently in the Coursera [R Programming](https://www.coursera.org/learn/r-programming) course forum. Here I organized those questions and collected my replies to them.

Please note that these articles are not intended to be self-sufficient resources for learning R. If you are interested in R language, here are some good starts:

1. [Data Science Specialization](https://www.coursera.org/specializations/jhu-data-science) of JHU on Coursera (free auditing)
2. [swirl package](http://swirlstats.com) of R (R and swirl installation required)
3. [R語言翻轉教室](http://datascienceandr.org) (only for Mandarin-speaking users)

Besides, RStudio and R users around the world have contributed many cheatsheets which can be referred to anytime. Check [RStudio Cheat Sheets](https://www.rstudio.com/resources/cheatsheets/) for them.

For advanced R users. If you are interested in more detailed mechanisms of R grammar, you may refer to [Advanced R](http://adv-r.had.co.nz) written by Hadley Wickham, and [Advanced R Programming](https://www.coursera.org/learn/advanced-r).

## Getting started
* [Why R but not Excel](articles/R-over-Excel.md): Here I listed some advantages of R over Excel from my point of view.
* [Use R or RStudio](articles/R-or-RStudio.md): RStudio can't be executed without R. Still they have different advantages.
* [Chinese user names cause errors](articles/Chinese-user-names.md): If your computer user name comprise Chinese characters and you get errors when running RStudio, please refer to this article.
* [Use `<-` or `=`](articles/use-equal-or-arrow.md): Using either `<-` or `=` to assign values in R is a question related to personal preferences. I shared my own opinions here.
* [Why `strptime` returns NAs](articles/strptime-returns-NA.md): Languages from different system locales may cause some abnormalities. However we can change the locale settings within R scope without changing the whole OS.

## Data types
* ["Vectors" in R](articles/vector-in-R.md): Vectors in R don't have mathematical sense. Yet "mathematical vectors" and matrix operations can still be performed.
* [Number types](articles/integer-numeric.md): R has class "integer" and "numeric", they are different in memory management and capability to be manipulated.

## Data preprocessing
* [Difference between `[[]]` and `$`](articles/doublebrackets-and-dollarsign.md): There are various extract operators in R. In this short paragragh I explain the difference between `[[]]` and `$`, and provide a link to an even more comprehensive article written by another Community Mentor.
* [Factor levels and labels](articles/factor-levels-and-labels.md): Categorical data are called "factor" in R. This article explains what are factor levels and factor labels respectively.
* [Split data](articles/split-data.md): Data can be splited with specified categories. However the length of the factor variables matters.
* [Paste strings](articles/paste-arguments.md): Pasting various strings together is a plausible way to create variables. Here I introduce the two critical arguments, sep and collapse, of `paste` function in R.
* [Argument MARGIN for `apply`](articles/apply-margin.md): `apply` allows users to execute a function over dimensions of matrices or arrays. What if we assign multiple dimensions at a time?

## Comparison and ranking of data
* [Difference between `==` and `%in%`](articles/compare-twoequals-with-in.md): Both `==` and `%in%` are often used to find matches in data. Yet, they have one difference when we have multiple inputs to be compared in parallel with the target.
* [Order, rank, and sort](articles/order-rank-sort.md): These three functions are commonly used to make data into orders, but they are confusing with one another. This article tries to offer clarifications.

## Functional programming
* [Difference between `print` and `return` from a function](articles/print-and-return.md): Both `print` and `return` make objects "visible" outside the executed function, but only `return` truly returns values that can be saved for later use. Examples are provided in this article.

## Lexical scoping of R language

* [Lexical scoping](articles/lexical-scoping.md): This article demonstrates what would happen if an object is defined not only outside but also inside the function.
* [Constructor functions](articles/constructor-functions.md): With knowledge of lexical scoping, we are able to write a function which creates other functions.
* [Optimizing parameters](articles/optimizing.md): Another example showing how lexical scoping can help you optimize your interested parameters.

## Generic functions

* [How `mean` was created](articles/how-mean-created.md): The source codes of `mean` cannot be seen by simply typing `mean` in the console. This article demonstrates how to see them.

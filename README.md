# Coursera R Mentoring
_Mentoring records and my helping articles on Coursera (Under construction) (Last update: July 9, 2017)_

Some questions have been raised repeatedly in the Coursera [R Programming](https://www.coursera.org/learn/r-programming) course forum. Here I organized those questions and collected my replies to them.

Please note that these articles are not intended to be self-sufficient resources for learning R. If you are interested in R language, here are some good starts:

1. [Data Science Specialization](https://www.coursera.org/specializations/jhu-data-science) of JHU on Coursera (free auditing)
2. [swirl package](http://swirlstats.com) of R (R and swirl installation required)
3. [R語言翻轉教室](http://datascienceandr.org) (only for Mandarin-speaking users)

## Getting started
* [use "<-" or "="](use%3Dor%3C-.md): Using either `<-` or `=` to assign values in R is a question related to personal preferences. I shared my own opinions here.
* [strptime returns NAs](strptime-returns-NA.md): Languages from different system locales may cause some abnormalities. However we can change the locale settings within R scope without changing the whole OS.

## Data preprocessing
* [factor levels and labels](factor-levels-and-labels.md): Categorical data are called "factor" in R. This article explains what are factor levels and factor labels respectively.
* [split data](split-data.md): Data can be splited with specified categories. However the length of the factor variables matters.
* [paste strings](paste-arguments.md): Pasting various strings together is a plausible way to create variables. Here I introduce the two critical arguments, sep and collapse, of `paste` function in R.

## Comparison and ranking of data
* [Difference between "==" and "%in%"](compare%3D%3Dwith%25in%25.md): Both `==` and `%in%` are often used to find matches in data. Yet, they have one difference when we have multiple inputs to be compared in parallel with the target.
* [Order, rank, and sort](order-rank-sort.md): These three functions are commonly used to make data into orders, but they are confusing with one another. This article tries to offer clarifications.

## Lexical scoping of R language
If you are interested in more advanced mechanisms of R grammar, you may refer to [Advanced R](http://adv-r.had.co.nz) by Hadley Wickham. Here I provided two related questions for the materials of R Programming course.
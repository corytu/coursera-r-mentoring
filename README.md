# Coursera R Mentoring
_Mentoring records and my helping articles on Coursera (Last update: July 11, 2017)_

Some questions have been raised repeatedly in the Coursera [R Programming](https://www.coursera.org/learn/r-programming) course forum. Here I organized those questions and collected my replies to them.

Please note that these articles are not intended to be self-sufficient resources for learning R. If you are interested in R language, here are some good starts:

1. [Data Science Specialization](https://www.coursera.org/specializations/jhu-data-science) of JHU on Coursera (free auditing)
2. [swirl package](http://swirlstats.com) of R (R and swirl installation required)
3. [R語言翻轉教室](http://datascienceandr.org) (only for Mandarin-speaking users)

## Getting started
* [Use "<-" or "="](use-equal-or-arrow.md): Using either `<-` or `=` to assign values in R is a question related to personal preferences. I shared my own opinions here.
* [Why strptime returns NAs](strptime-returns-NA.md): Languages from different system locales may cause some abnormalities. However we can change the locale settings within R scope without changing the whole OS.

## Data preprocessing
* [Factor levels and labels](factor-levels-and-labels.md): Categorical data are called "factor" in R. This article explains what are factor levels and factor labels respectively.
* [Split data](split-data.md): Data can be splited with specified categories. However the length of the factor variables matters.
* [Paste strings](paste-arguments.md): Pasting various strings together is a plausible way to create variables. Here I introduce the two critical arguments, sep and collapse, of `paste` function in R.
* [Argument MARGIN for apply](apply-margin.md): `apply` allows users to execute a function over dimensions of matrices or arrays. What if we assign multiple dimensions at a time?

## Comparison and ranking of data
* [Difference between "==" and "%in%"](compare-twoequals-with-in.md): Both `==` and `%in%` are often used to find matches in data. Yet, they have one difference when we have multiple inputs to be compared in parallel with the target.
* [Order, rank, and sort](order-rank-sort.md): These three functions are commonly used to make data into orders, but they are confusing with one another. This article tries to offer clarifications.

## Lexical scoping of R language
This section is for advanced R users. If you are interested in more advanced mechanisms of R grammar, you may refer to [Advanced R](http://adv-r.had.co.nz) by Hadley Wickham. Here I provided three related questions for the materials of R Programming course.

* [Lexical scoping](lexical-scoping.md): This article demonstrates what would happen if an object is defined not only outside but also inside the function.
* [Constructor functions](constructor-functions.md): With knowledge of lexical scoping, we are able to write a function which creates other functions.
* [Optimizing parameters](optimizing.md): Another example showing how lexical scoping can help you optimize your interested parameters.

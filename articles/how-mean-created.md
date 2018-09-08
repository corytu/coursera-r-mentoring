One learner execute `mean`, hoping to see the source code of `mean` function. However, he saw this:

```
function (x, ...) 
UseMethod("mean")
<bytecode: 0x7fa151cbe038>
<environment: namespace:base>
```

, which is not really code.

_Question: How to know how `mean` was created?_

----

It needs some advanced knowledge of R language to fully understand the mechanism, which is covered in another course, [Advanced R Programming](https://www.coursera.org/learn/advanced-r). If you're not aiming to be an R developer, that course may not necessary though.

Still you can try these codes:

```r
methods(mean)
# You should see several elements looking like mean.XXX
getAnywhere(mean.default)
# This is the source code you want
```

Here is some brief explanation. In fact, `mean` is a "generic function" in R, which means that it can return different kinds of values depending on the class of inputs. The supported classes can be found in the results of `methods(mean)`, so we know the `mean` function can actually calculate the mean of numeric values, or a series of dates or time points. Users don't usually specify the method explicitly, but just keep in mind that things work in that way.

There are also discussions on StackOverflow, like [Looking at internal Methods](https://stackoverflow.com/questions/5835312/looking-at-internal-methods).

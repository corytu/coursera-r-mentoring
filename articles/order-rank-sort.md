R rookies often confuse `rank` with `order`. It's OK because they are truly confusing, and both of them give users "ranking" information. The following article elaborates how they are different.

Let's take an easy example to show the mechanisms. Consider the situation that only one vector is given.

```r
set.seed(1)
rate <- sample(10, 5)
rate
# 3 4 5 7 2
order(rate)
# 5 1 2 3 4
rank(rate)
# 2 3 4 5 1
```

Now, what `order` gives you is, in this example, that "__the _5th_ element of rate is the smallest one__", so you have 5 coming in the first. `order` accepts multiple vectors as input arguments to break ties. Thus, for `order` function, you can do something like this:

```r
rate[order(rate)]
# 2 3 4 5 7
# Permute "rate" in ascending order
```

On the other hand, `rank` gives you that "__the rank of the last element among rate elements is the *1st*__", so the 5th returned value is 1.

Besides `order` and `rank`, we have `sort` in R to sort a vector into orders. In this example, `sort(rate)` is equivalent to `rate[order(rate)]`.

By default, all these three functions return an ascending order.

I know it takes some time to digest. Take it easy and feel free to ask further questions. :)
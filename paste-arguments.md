_Question: `paste` function has two arguments besides the ellipsis: "sep" and "collapse". What do they do?_

---

__The short answer is: "sep" separates the terms, and "collapse" separates the results.__

Let's go through an easy example to see what that means.

```r
x <- letters[1:3]
y <- letters[24:26]
# Create two chracter vectors

paste(x, y, sep = ".")
# "a.x" "b.y" "c.z"
# "." separates x and y elements respectively

paste(x, y, sep = ".", collapse = "+")
# "a.x+b.y+c.z"
# "+" further separates the result of the above pasted results
```
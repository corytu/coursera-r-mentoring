When using `strptime` function in R, by default, R recognizes strings (and then converts them into time format) based on __your current locale setting of your OS__.

Hence, to resolve the NA issue, you have to change the locale options of R, or otherwise change that of your OS. According to [this StackOverflow post](http://stackoverflow.com/questions/16347731/how-to-change-the-locale-of-r-in-rstudio), you can do that by:
```r
Sys.setlocale("LC_ALL","English")
```
Or, you can also change "LC_TIME" instead of chaging "LC_ALL", which alters all locale-related settings.
```r
Sys.setlocale("LC_TIME", "en")          # Solaris 7: details are OS-dependent
Sys.setlocale("LC_TIME", "en_US.utf8")  # Modern Linux etc
Sys.setlocale("LC_TIME", "en_US")       # Mac OS
Sys.setlocale("LC_TIME", "English")     # Windows
```

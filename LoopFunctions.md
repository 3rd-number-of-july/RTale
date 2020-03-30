Loop Functions
================
3rd number of July

1.  lapply()
2.  sapply()
3.  apply()
4.  tapply()
5.  mapply()

### Lapply()

#### Algorythm

**Lapply()** does the following series of operations:

1.  it loops over a list, iterating over each element in that list
2.  it applies a *specified function* to each element of the list
3.  it always returns a **list (l-apply)**

#### Arguments

1.  a list *X*
2.  a function *FUN*
3.  other arguments via *‘…’* argument

<!-- end list -->

``` r
x <- list(1:5)

lapply <- lapply(x, mean)
print(lapply)
```

    ## [[1]]
    ## [1] 3

``` r
class(lapply)
```

    ## [1] "list"

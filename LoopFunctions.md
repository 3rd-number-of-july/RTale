---
title: "Loop Functions"
author: "3rd number of July"
output: 
     html_document:
          code_fonding: non
          toc: TRUE
          toc_float: TRUE
          toc_depth: 1
          number_sections: TRUE
          highlight: 'zenburn'
          theme: readable
          
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

# Lapply()

## Algorythm
**Lapply()** does the following series of operations:

1. it loops over a list, iterating over each element in that list
2. it applies a *specified function* to each element of the list
3. it always returns a **list (l-apply)**

## Arguments
1. a list *X*
2. a function *FUN*
3. other argument

## Code example
```{r lapply, echo=TRUE}
x <- list(1:5) #this list contains just ONE element

lapply <- lapply(x, mean)
print(lapply)

class(lapply) # output of LAPPLY is always a list
```

# Sapply()

Sapply() behaves similarly to lapply(), but it will try to **simlify (s-apply)** the result

|Result of sapply | Returned class |
|:---------------:|:--------------:|
|List with each element of length 1|`vector`|
|List with each element of the same length > 1|`matrix`|
|Something else|`list`|

# Tapply()

Tapply() is used to apply a function *over subsets of a vector*

## Arguments

1. `x` is a vector
2. `INDEX` is a factor / list of factors
3. `Function`
4. `...`
5. `simplify` - should it simplify the result like sapply

# Apply()

Apply() is used to evaluate a function **over the margins of an array**
* often used to apply a function to *the rows / columns of a matrix*

## Arguments

1. `x` is an array
2. `MARGIN` is an unteger vector indicating which margins should be 'retained'
     + `1` for rows
     + `2` for columns and so on
3. `Function`
4. `...`

## Code example
```{r}
x <- matrix(1:10, 2, 5)
print(x)

apply1 <- apply(x, 1, mean) #take the mean of each row
print(apply1)

class(apply1)

apply2 <- apply(x, c(1,2), function(y) {y-1}) 
# apply the funtion to each dimension (2 out of 2)
print(apply2)
class(apply2)
```

# Mapply()

Mapply() is used to apply a function **in parallel** 

## Arguments
1. `Function`
2. `...` contains R objects to apply over
3. `MoreArgs` is a list of other arguments to `function`
4. `Sumplify` should the result be simplify

## Code example
```{r}
mapply <- mapply(rep, 1:4, 4:1) # instead of typing 
     # list(rep(1, 4), rep(2, 3), rep(3, 2), rep(4, 1))
print(mapply)
```




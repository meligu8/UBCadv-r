---
title: "Functions"
author: "Susannah"
---

# Quiz
1. The three elements of a function are the name of the function, the arguments of the function, and the guts of the function. *X* _Functions don't have to have names in `R`, but the environment matters. Remember that time Hadley's plyr masked a function in another package and you got really confused?_
2. 11
3. `1 + 2 * 3`
4. `mean(x = c(1:10, NA), na.rm = TRUE)`
5. No - the `stop` should be within the function, not the arguments to the function.
6. An infix function is a function like `+,-,/` that generally goes inbetween arguments. I don't know what a replacement function is. *X*
7. `on.exit()`

# Functional components
1. `class` allows you to tell if an `R` object is a function. I tried to use `attributes()` to find out whether functions were primitive or not, but returned `NULL` for many functions - including functions I knew to be not primitive. Just typing the name of the function without parentheses will tell you whether the function is primitive or not. `environment(function)` returns `NULL` for all primitive functions.
2. 

```r
objs <- mget(ls("package:base"), inherits = TRUE)
nullenv <- function(func) {
    is.null(environment(func))
}
funs <- Filter(is.function, objs)
nulls <- Filter(nullenv, funs)

arg <- lapply(funs, formals)  # get formals
counts <- sapply(arg, length)  # count formals
maxcount <- which.max(counts)  #find most args
zeros <- which(counts == 0)  #no args
```

  * `scan` has the most arguments - 896.
  * infixes, math functions, casts, control flow, system calls, and debugging functions have no arguments. These are typically primitive functions (see output of `sapply(names(zeros),environment`). Since primitive functions handle arguments a bit differently than other functions, I guess it's best to avoid the problem altogether by not having arguments at all!
  * 
  
  ```r
  objs <- mget(ls("package:base"), inherits = TRUE)
  
  nullenv <- function(func) {
      # returns true if function environment is null
      is.null(environment(func))
  }
  
  funs <- Filter(is.function, objs)
  nulls <- Filter(nullenv, funs)
  ```

  

# Lexical scoping

# EOiaFC

# Function Arguments

# Special Calls

# Return Values

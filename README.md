# Lab 02: R Package and R Review

-   Create an R package called `{ltrsum}` that provides summaries of
    letters of string vectors. The functions should be

    -   `lt_lcount()`:
        -   Input: A character vector `x`.
        -   Output: A numeric vector of length 26 that contains the
            counts of each letter.
        -   Example:

        ``` r
        x <- c("Hello", "Goodbye")
        lt_lcount(x = x)
        #> a b c d e f g h i j k l m n o p q r s t u v w x y z 
        #> 0 1 0 1 2 0 1 1 0 0 0 2 0 0 3 0 0 0 0 0 0 0 0 0 1 0
        ```
    -   `lt_lprop()`:
        -   Input: A character vector `x`.
        -   Output: A numeric vector of length 26 that contains the the
            proportions of each letter.
        -   Example:

        ``` r
        x <- c("Hello", "Goodbye")
        lt_lprop(x = x)
        #>       a       b       c       d       e       f       g       h       i       j 
        #> 0.00000 0.08333 0.00000 0.08333 0.16667 0.00000 0.08333 0.08333 0.00000 0.00000 
        #>       k       l       m       n       o       p       q       r       s       t 
        #> 0.00000 0.16667 0.00000 0.00000 0.25000 0.00000 0.00000 0.00000 0.00000 0.00000 
        #>       u       v       w       x       y       z 
        #> 0.00000 0.00000 0.00000 0.00000 0.08333 0.00000
        ```
    -   `lt_wcount()`:
        -   Input: A character vector `x`
        -   Output: A list of length 26. Each element of the list is a
            numeric vector containing the counts of letter occurrences
            in a word for each letter.
        -   Example:

        ``` r
        x <- c("Hello", "Protozoology")
        lt_wcount(x)
        #> $a
        #> 
        #> 0 
        #> 2 
        #> 
        #> $b
        #> 
        #> 0 
        #> 2 
        #> 
        #> $c
        #> 
        #> 0 
        #> 2 
        #> 
        #> $d
        #> 
        #> 0 
        #> 2 
        #> 
        #> $e
        #> 
        #> 0 1 
        #> 1 1 
        #> 
        #> $f
        #> 
        #> 0 
        #> 2 
        #> 
        #> $g
        #> 
        #> 0 1 
        #> 1 1 
        #> 
        #> $h
        #> 
        #> 0 
        #> 2 
        #> 
        #> $i
        #> 
        #> 0 
        #> 2 
        #> 
        #> $j
        #> 
        #> 0 
        #> 2 
        #> 
        #> $k
        #> 
        #> 0 
        #> 2 
        #> 
        #> $l
        #> 
        #> 0 1 2 
        #> 0 1 1 
        #> 
        #> $m
        #> 
        #> 0 
        #> 2 
        #> 
        #> $n
        #> 
        #> 0 
        #> 2 
        #> 
        #> $o
        #> 
        #> 0 1 2 3 4 5 
        #> 0 1 0 0 0 1 
        #> 
        #> $p
        #> 
        #> 0 
        #> 2 
        #> 
        #> $q
        #> 
        #> 0 
        #> 2 
        #> 
        #> $r
        #> 
        #> 0 1 
        #> 1 1 
        #> 
        #> $s
        #> 
        #> 0 
        #> 2 
        #> 
        #> $t
        #> 
        #> 0 1 
        #> 1 1 
        #> 
        #> $u
        #> 
        #> 0 
        #> 2 
        #> 
        #> $v
        #> 
        #> 0 
        #> 2 
        #> 
        #> $w
        #> 
        #> 0 
        #> 2 
        #> 
        #> $x
        #> 
        #> 0 
        #> 2 
        #> 
        #> $y
        #> 
        #> 0 1 
        #> 1 1 
        #> 
        #> $z
        #> 
        #> 0 1 
        #> 1 1
        ```
    -   `lt_wprop()`:
        -   Input: A character vector `x`

        -   Output: A list of length 26. Each element of the list is a
            numeric vector containing the proportions of letter
            occurrences in a word for each letter.

        -   Example:

            ``` r
                    x <- c("Hello", "Protozoology")
                    lt_wprop(x)
            #> $a
            #> 
            #> 0 
            #> 1 
            #> 
            #> $b
            #> 
            #> 0 
            #> 1 
            #> 
            #> $c
            #> 
            #> 0 
            #> 1 
            #> 
            #> $d
            #> 
            #> 0 
            #> 1 
            #> 
            #> $e
            #> 
            #>   0   1 
            #> 0.5 0.5 
            #> 
            #> $f
            #> 
            #> 0 
            #> 1 
            #> 
            #> $g
            #> 
            #>   0   1 
            #> 0.5 0.5 
            #> 
            #> $h
            #> 
            #> 0 
            #> 1 
            #> 
            #> $i
            #> 
            #> 0 
            #> 1 
            #> 
            #> $j
            #> 
            #> 0 
            #> 1 
            #> 
            #> $k
            #> 
            #> 0 
            #> 1 
            #> 
            #> $l
            #> 
            #>   0   1   2 
            #> 0.0 0.5 0.5 
            #> 
            #> $m
            #> 
            #> 0 
            #> 1 
            #> 
            #> $n
            #> 
            #> 0 
            #> 1 
            #> 
            #> $o
            #> 
            #>   0   1   2   3   4   5 
            #> 0.0 0.5 0.0 0.0 0.0 0.5 
            #> 
            #> $p
            #> 
            #> 0 
            #> 1 
            #> 
            #> $q
            #> 
            #> 0 
            #> 1 
            #> 
            #> $r
            #> 
            #>   0   1 
            #> 0.5 0.5 
            #> 
            #> $s
            #> 
            #> 0 
            #> 1 
            #> 
            #> $t
            #> 
            #>   0   1 
            #> 0.5 0.5 
            #> 
            #> $u
            #> 
            #> 0 
            #> 1 
            #> 
            #> $v
            #> 
            #> 0 
            #> 1 
            #> 
            #> $w
            #> 
            #> 0 
            #> 1 
            #> 
            #> $x
            #> 
            #> 0 
            #> 1 
            #> 
            #> $y
            #> 
            #>   0   1 
            #> 0.5 0.5 
            #> 
            #> $z
            #> 
            #>   0   1 
            #> 0.5 0.5
            ```

-   Your package should have no dependencies.

-   Make sure to commit and push regularly.

-   Make sure you have fulfilled the following criteria:

    1.  Functions work on test cases above.
    2.  Functions are well documented.
    3.  DESCRIPTION file is complete.

-   Learning Objectives

    -   [R
        Packages](https://dcgerard.github.io/advancedr/02_packages.html).

## Hints:

-   If you are used to `{stringr}`, this cheat sheet might help:
    <https://stringr.tidyverse.org/articles/from-base.html>

-   In particular, try including the following equivalent to
    `str_count()` as two unexported functions in your package

    ``` r
    count_match <- function(x) {
      if (length(x) == 1) {
        if (x == -1) {
          return(0)
        } else {
          return(1)
        }
      } else {
        return(length(attr(x, "match.length")))
      }
    }
    letter_count <- function(x, pattern) {
      loc <- gregexpr(pattern = pattern, text = x, fixed = TRUE)
      sapply(loc, count_match)
    }
    letter_count(c("hello", "goodbye", "blah"), "o")
    #> [1] 1 2 0
    ```

-   The R object `letters` from the `{base}` package might prove useful.

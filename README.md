# There-are-now-3-different-R-pipes

R 4.1.0 has been released and has a couple of handy new features.

One is a shorthand syntax for defining functions. Now, instead of writing, for example

triple <- function(x) x * 3

you can use the more concise syntax

triple <- \(x) x * 3

which may come in handy when using anonymous functions in apply-type calls.

More interesting, though, is the addition of a native pipe operator to R, given by |>, i.e. a pipe and a greater-than sign. As of R 4.1.0, the following are equivalent.

triple(4)
4 |> triple()

This is similar to the functionality previously provided by the magrittr package (often through dplyr and tidyr):

library(magrittr)
4 %>% triple

but saves you loading any add-on packages.

In fact, there already was a pipe of sorts in base R, as John Mount points out: in the form of the ->.; ‘operator’ (assign to a variable called ., then terminate with the rarely-used semicolon):

4 ->.; triple(.)

As a result there are now four different ways of writing the same function call as a one-liner in R version 4.1.0:

triple(4)
4 %>% triple
4 ->.; triple(.)
4 |> triple()

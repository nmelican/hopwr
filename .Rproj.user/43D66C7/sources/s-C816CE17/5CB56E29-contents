# Chapter 2: Packages and help pages


# ========PACKAGES: GGPLOT2--QPLOT=============================
# To install a package:
install.packages("x")
# Where x is the package name
# commonly used packages: tidyverse, XML, dplyr, ggplot2, lubridate
install.packages("tidyverse")
# you can also install multiple packages at the same time using the c()
# (concatenate) function:
install.packages(c("ggplot2", "tidyverse", "xml"))

# Load a package (before using it):
library(x)
# Where x is the package name
library(ggplot2)
# unfortunately you can only load one package at a time

# packages contain additional tools that could help you accomplish things.
# For example, ggplot2 is a package meant to be used to visualise data.
# it has an easy plotting application/function called qplot.
# (just be sure to include the parentheses when calling up qplot,
# or you'll just end up with the code for the function.)
qplot
qplot()

# qplot can make quick graphs, but it can only work with data and can't do
# anything without it (that's why calling up just qplot() on the prompt
# would only display an empty box).
# so let's give it some data to work with. We're assigning values for
# object x using the concatenate or c() function:
x <- c(-1, -0.8, -0.6, -0.4, -0.2, 0, 0.2, 0.4, 0.6, 0.8, 1)
x
# calling up x after defining the object just shows us that it really
# has been defined as such.

# now let's define the y object as dependent on x:
y<-x^3
y

# now, let's plot x against y:
qplot (x, y)

# this should produce a scatterplot where R paired each value of the first
# object (x) with a value on the second object (y). This wouldn't work if
# the two variables have an unequal number of values:
xx <- c(-1, -0.7, -0.6, -0.4, -0.1, 0.3, 0.4, 0.8, 1)
yy <- c(-1, -0.6, -0.1, 0.3, 0.8, 1)
qplot (xx, yy)
# shows the error:
# Error: Aesthetics must be either length 1 or the same as the data (9): y

# Another graph type that qplot can handle is the histogram, or bar chart.
# You can use only one object/variable for this:
x1 <- c(1, 2, 2, 2, 3, 3)
qplot(x1, binwidth = 1)
# binwidth is an argument that affects how your histogram is displayed.
# try running the histogram without binwidth:
qplot(x1)

# another example of a histogram:
x2 <- c(1, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 4)
qplot(x2, binwidth = 1)

# and another one:
x3 <- c(0, 1, 1, 2, 2, 2, 3, 3, 4)
qplot(x3, binwidth = 1)

# ========BACK TO OUR DICE: PLOTTING 10,000 ROLLS==========================
# The replicate() function is a handy way to doing functions many times.
replicate(3, 1 + 1)
# Where 3 is the number of times you want an operation repeated, and the next
# argument is the operation to be repeated.

# so to roll our dice 10 times:
replicate(10, roll())

# now repeat 10,000 times, then graph the result:
rolls <- replicate(10000, roll())
qplot(rolls, binwidth = 1)

# or maybe, a function?
rollfunc <- function() {
  rolls <- replicate(10000, roll())
  qplot(rolls, binwidth = 1)
}
rollfunc()


# ========GETTING HELP=============================
# R has over a thousand functions, which is a lot to take in. Getting help
# is easy though, as each function has a help page which can be invoked
# by typing ? and the name of the function:
?sqrt
?log10
?sample

# You can also search for a function you may have forgotten the command for
# by typing in two quotation marks (??) before the keyword:
??modulo
??log

# ========SAMPLE: SPECIFYING PROBABILITY=============================
# Let's return to our original roll() function:
roll <- function() {
  die <- 1:6
  dice <- sample(die, size = 2, replace = TRUE)
  sum(dice)
}

# Say you want to rig the dice by saying that numbers 1:5 occurs at a
# probability of 1/8 each, and the number 6 occurs at a probability
# of 3/8 each, you need to specify this using the prob argument:
roll <- function() {
  die <- 1:6
  dice <- sample(die, size = 2, replace = TRUE,
                 prob = c(1/8, 1/8, 1/8, 1/8, 1/8, 3/8))
  sum(dice)
}

# another way of doing this is by using decimals to represent fractions:
roll <- function() {
  die <- 1:6
  dice <- sample(die, size = 2, replace = TRUE,
                 prob = c(0.125, 0.125, 0.125, 0.125, 0.125, 0.375))
  sum(dice)
}
# it's good enough though that R understands fractions in their raw form

# now, to test:
rolls <- replicate(10000, roll())
qplot(rolls, binwidth = 1)
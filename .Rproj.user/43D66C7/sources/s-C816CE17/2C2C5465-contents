# Chapter 1: The very basics


# ========THE R USER INTERFACE=============================
# basic math operations: addition
1 + 1

# view all integers between x and y
100:130

# if you run an incomplete command, R will break to the next line until you type a
# valid string that completes the command, then runs it. hit the escape button
# to terminate or cancel the command
5 -
  
  1

# if R doesn't understand the command, it returns an error
5 % 4

# more valid maths
# subtraction
10 - 3

# multiplication
5 * 9

# division
94 / 2

# exponents
2 ^ 3

# modulo: displays remainder in a division operation
9 %% 2

# computations with parentheses
((((5 + 2) * 3) - 6) / 3)

# check answer (should be 5)
5 + 2
7 * 3
21 - 6
15 / 3


# ========OBJECTS=============================
# create a virtual die
1:6

# assigning value to objects
a <- 1
a
a + 2

# create an actual object that is a die
die <- 1:6

# TIP: list all objects in the current workspace
ls()

# perform operations on all values inside of die
die * 3
die / 2
die * die

# observe what happens when die is operated upon using unequal number of values
die * 1:4
# This warning message appears:
# Warning message:
#   In die * 1:4 :
#   longer object length is not a multiple of shorter object length

# This is what happened (what R did):
# die   *   num     =
# 1     *   1       1
# 2     *   2       4
# 3     *   3       9
# 4     *   4       16
# 5     *   1       5
# 6     *   2       12

# R cycled through the multiplicand until all terms in die were multiplied
# by a corresponding number on the multiplicand side, aka, Element-wise operation

# But R can also do matrices:
# inner multiplication:
die %*% die

# outer multiplication:
die %o% die

# which can make a nifty times tables:
timestables <- 1:10
timestables %o% timestables


# ========FUNCTIONS=============================
# Round off a number
round(pi) #(3.1415...)

# Factorial function (that one denoted by an exclamation point (!)--
# multiplies numbers in the series in ascending order)
factorial(3) #1 * 2 * 3

# Get the mean
mean(die)

# Nesting functions--round off the mean of die
# R works from the innermost parentheses to the outermost ones
round(mean(die))

# Rolling the die--using the sample function
sample(x = die, size = 2)
# where 'x' is the thing/object where you'll get the sample from,
# and size is the number of samples to be drawn.

# so if you just want one number, size = 1 (also, you can just say 'die'
# instead of x = die. Most of the time functions in R refer to the first
# argument as the subject (or rather the object) that will be used for
# that function. and separate functions with a comma):
sample(die, size = 1)

# TIP: To see all valid arguments for a function, use:
args(round)

# so you can round off pi to two decimal places:
round(pi, digits = 2)

# how about sample's arguments?
args(sample)

# to simulate two dice which may roll the same number at once, use the
# replace argument. It tells R that it can use the same values over again:
sample(die, size = 2, replace = TRUE)
# the replace argument requires a boolean value, TRUE or FALSE. These are CASE
# SENSITIVE, so you must write TRUE and FALSE in ALL CAPS EVERYTIME.


# ========WRITING YOUR OWN FUNCTIONS=============================

# a fancy way to roll the dice--save the operations as an object:
dice <- sample(die, size = 2, replace = TRUE)
dice
sum(dice)

# but this method fixes its value in R's memory.
# doing it as a function will ensure a random result is drawn, every time.
# it's like creating an object, but it has code, not just data:
roll <- function() {
  die <- 1:6
  dice <- sample(die, size = 2, replace = TRUE)
  sum(dice)
}

# to invoke this function, just type 'roll' and add parentheses:
roll()

# don't forget the parentheses. R will just display the code behind the
# function if you don't use the parentheses:
roll

# another function: what if you want to see just the numbers that the dice draw?
rolled <- function() {
  die <- 1:6
  sample(die, size = 2, replace = TRUE)
}

# see it in action:
rolled()
rolled()
rolled()

# ========CUSTOM FUNCTIONS WITH ARGUMENTS=============================
# Take this modified roll() code (now called roll2). It doesn't define the
# value for the 'thang' object:
roll2 <- function() {
  dice <- sample(thang, size = 2, replace = TRUE)
  sum(dice)
}

# roll (sorry) it:
roll2()
# error shows up:
# Error in sample(thang, size = 2, replace = TRUE) : 
#   object 'thang' not found

# you can define 'thang' when you run roll2 by making 'thang' an argument of
# the roll2 function:
roll2 <- function(thang) {
  dice <- sample(thang, size = 2, replace = TRUE)
  sum(dice)
}

# but don't just go rolling (sorry again) without properly defining the
# 'thang' argument, as you will see below:
roll2()
roll2(thang)

# you have to specify the value of thang by treating it as a real argument
# demanding real answers:
roll2(thang = 1:10)

# or you can set the default value of 'thang' when writing the function:
roll2 <- function(thang = 1:10) {
  dice <- sample(thang, size = 2, replace = TRUE)
  sum(dice)
}

# TIP: It's good practice to save your work as an R script.
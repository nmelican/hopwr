# Chapter 3: R Objects

# We're dealing with a deck of cards to learn about storing, retrieving, 
# and changing data values in the computer's memory.

# ========ATOMIC VECTORS=============================
# a simple vector of data, like the die
die

# to check whether an object is an atomic vector:
is.vector(die)

# atomic vectors can hold as simple as one value:
five <- 5
five
is.vector(five)

# to check the length of an atomic vector:
length(five)
length(die)

# each atomic vector can only store one type of data.
# to check the data type a vector holds, use typeof().
typeof(x)

# there are six types of data that can be stored in a vector:

# 1. doubles/numerics: numbers with decimals. The default
#     type of data that R stores
die <- c(1, 2, 3, 4, 5, 6)
typeof(die)

# integers: whole numbers, indicated with the letter L
#     immediately after the number, e.g., 1L
int <- c(-1L, 2L, 4L)
typeof(int)

# characters: alphanumeric strings, always with quotes, e.g., "hello world"
text <- c("hello", "world")
typeof(text)
typeof("Hello")

# logicals: boolean values, always in ALL CAPS, e.g, TRUE, FALSE
3 < 4
3 > 4
logic <- c(TRUE, FALSE, TRUE)
logic
typeof(logic)

# complex: complex numbers denoted with i immediately
#     after the number, e.g, 2i
comp <- c(1 + 1i, 3 + 1i)
comp
typeof(comp)

# raw: raw, binary data. simplest way to assign raw data is through
#     the raw() function, e.g., raw(3), which creates an empty,
#     raw vector of three bytes' length.
raw(4)
typeof(raw(4))

# Create a vector containing the face names of cards in a royal flush:
hand <- c("ace", "king", "queen", "jack", "ten")
typeof(hand)

# ========ATTRIBUTES: NAMES=============================
# Attributes are characteristics of an R object. It doesn't affect
# the data, and it is not displayed when an object is called,
# but some processes may rely on attributes to determine what to
# do with an object.

# see the attributes of an R object or an atomic vector by using:
attributes(die)
# if attributes of an object are undefined, as in this case,
# R returns NULL.

# NAMES are the most common attribute assigned to objects. Specify the
# names of values in an object with:
names(die) <- c("one", "two", "three", "four", "five", "six")

# once stored, invoke the names with:
names(die)

# now check on die's attributes:
attributes(die)

# and when you invoke die:
die
# it shows the names lined up with the values in it.

# names won't affect operations on the values they are associated with:
die * 2

# you can use the names() function to rename values in the vector.
# if you want to remove the names, run
names(die) <- NULL


# ========ATTRIBUTES: DIM=============================
# the dim() attribute transforms an atomic vector into an n-dimensional
# array by specifying the number of dimensions it has.
# to make die a 2x3 matrix:
dim(die) <- c(2, 3)
die

# or a 1x2x3 hypercube (I don't know how this looks in real life TBH):
dim(die) <- c(1, 2, 3)
die


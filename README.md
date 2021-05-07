# Distributed MapReduce
A distributed MapReduce implementation built with using the Pi calculus within the programming language Pict

## Authors
Chris Turgeon and Daniel Tabin

## Runing Instructions
Our program requires the types of the input, intermediate, and output keys and values to be specified.  In our solution, these are declared as K1 V1, K2 V2, and K2 V3.  

To run problem 1, simply run mapreduce_prob1.pi, and to run problem 2, simply run mapreduce_prob2.pi.  The only differences between these files is the different map, reduce, and compare functions (as well as their helpers), and the different types for K1-3 and V1-3

# Running Yourself
To run your own map, reduce, and compare on our engine, simply replace the map, reduce and compare functions in the file, as well as the types, to be geared to your own solution.

Also, it should be noted that we split our compare function into two functions.  One is used for sorting, and one is a boolean to check equality.  This is done as in problem 1, we want to sort on substring length, but a compartator that only checks substring length will decide that words such as "tis" and "his" are equal, which is cearly false.  Thus our mapreduce function technically takes four arguments; however both the equality checking function, and the sorting comparitor function can be considered to be parts of a single overall comparitor function.

Problem 2 takes the approach of generating localized statistics per line, then reduce will take the summation and average them all. Our word statistics work completely perfectly but I think we made assumptions for the character calculations that differed from the given solution. We assumed that characters is the total number of characters in the "sonnet" or input then we assumed characters per word involves stripped words. That is, all non-alphanumeric characters were removed from the words during map processing. So for example "Jerome's" would become "Jeromes" and then chars per word is calculated based on that.

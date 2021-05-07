# Distributed MapReduce
A distributed MapReduce implementation built with using the Pi calculus within the programming language Pict

## Authors
Chris Turgeon and Daniel Tabin

## Runing Instructions
Our program requires the types of the input, intermediate, and output keys and values to be specified.  In our solution, these are declared as K1 V1, K2 V2, and K3 V3.  These types are specified to statically check that correct types are used within the map, reduce, and compare functions.  To compile and run a Pict file, simply do the following:

```
pict <FILE_NAME>.pi -o a.out
./a.out
```

## Code
We present two examples, namely problem1.pi and problem2.pi, of using the MapReduce engine to solve a problem.  To run your own MapReduce solution on our engine, simply replace the map, reduce and compare functions in the file, as well as the types in the top of the file, to be geared to your own solution.

## Additional Description
It should be noted that we split our compare function into two functions.  One is used for sorting and one is a boolean to check equality.  This is done within problem1.pi because we want to sort on substring length, but a comparator that only checks substring length will decide that words such as "tis" and "his" are equal, which is clearly false.  Thus our MapReduce function technically takes four arguments; however both the equality checking function, and the sorting comparitor function can be considered to be parts of a single overall comparator function.

Problem 2 takes the approach of generating localized statistics per line, then reduce will take the summation and average them all. We assumed that characters is the total number of characters in the "sonnet" or input then we assumed characters per word involves stripped words. That is, all non-alphanumeric characters were removed from the words during map processing. So for example "Jerome's" would become "Jeromes" and then chars per word is calculated based on that.

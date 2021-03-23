# DistributedMapReduce
A distributed MapReduce implementation in the actor model using Pict

# Authors
Daniel Tabin [tabind] and Chris Turgeon [Turgec]

# Runing instructions
Our program requries the types of the input, intermediate, and output keys and values to be specified.  In our solution these are declared as K1 V1, K2 V2, and K2 V3.  In this homework we declare these at the top of each file, and have seperate files for each problem.  In a real worl situation, one would manually change these values.  Pict cannot take command line arguments, but if it could, this could be another option.

To run problem 1, simply run mapreduce_prob1.pi, and to run problem 2, simply run mapreduce_prob2.pi.  The only differences between these files is the different map, reduce, and compare functions (as well as their helpers), and the different types for K1-3 and V1-3

To run your own map, reduce, and compare on our engine, simply replace the map reduce and compare functions in the file, as well as the types.

Also, it should be noted that we split our compare function into two functions.  One is used for sorting, and one is a boolean to check equality.  This is done as in problem 1, we want to sort on substring length, but a compartator that only checks substring length will decide that words such as "tis" and "his" are equal, which is cearly false.  Thus our mapreduce function technically takes four arguments; however both the equality checking function, and the sorting comparitor function can be considered to be parts of a single overall comparitor function.
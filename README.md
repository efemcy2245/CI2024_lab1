In this lab we try to solve the set-cover problem.

In this README there is an explanation of the algorithm:
- the entire experiment is inside one method ( experiment ), in this method we create the dataset SETS, COSTS using
  as parameters NUM_SETS , UNIVERSE_SIZE , DENSITY given in input,
- we create the starting point ( the first solution ) and we try to improve it using a multiple mutation Hill Climber,
  we create a new solution using this multiple mutation function,
- for the first time we don't know if the solution is valid or not, so we are considering in our solution the number of True
  value inside our solution, if in the both new solution and the actual solution are not valid, then we compare the number of True,
  more True value our solution have then more probably we modify the right elements to get a solution that is at least valid.
- the next step is to compare 2 solutions that are valid, we compare their fitness and we use the best as new_solution.
  - at each step we reduce the density_method variable that is used in the method multiple_mutation to decide what is the "exploration value",
    ( more value we modify and more we get a different solution). The value is reduced of 5% at each step, we reduce the exploration.
  - if for 10_000*0.02=200 loops the algorithm don't find any new solution, then we are guessing that we are in a local minimum and at every steps
     we increase the exploration value.
  - if also using larger exploration value produce a solution, then we change directly the algorithm after 10_000*0.06=600 loops, we use the single tweak
    to improve our solution
  - if for 10_000*0.75=7500 loops the algorithm is yet using multiple mutation Hill Climber, we force the algorithm to find the solution modifying a single element,
    to create in the last part of the experiment more precise changing

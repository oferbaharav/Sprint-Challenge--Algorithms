#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I

a) O(n) - linear
When n is 10 it runs 10 times through the loop, when n is 100 it runs 100 times through the loop. Therefore it's Big O of order n


b) O(n * log(n))

The outer loop is running n times but the inner loop is doubling a number each time until it's bigger than i, so it's n * log(n)



c) O(n)

It's basically calculating that for 10 bunnies you get 20 ears recursively

## Exercise II

We have n stories and we throw the egg from under f to prevent it breaking and above it to get it broken. We need to find the value of f (floor number) such that number of throws + number of eggs broken is minimized.

--------


If the egg breaks after dropping from ‘fth’ floor, then we only need to check for floors lower than ‘f’ with remaining eggs as some floor should exist lower than ‘f’ in which egg would not break; so the problem reduces to f-1 floors and n-1 eggs.
If the egg doesn’t break after dropping from the ‘fth’ floor, then we only need to check for floors higher than ‘f’; so the problem reduces to ‘k-f’ floors and n eggs.
Since we need to minimize the number of trials in worst case, we take the maximum of two cases. We consider the max of above two cases for every floor and choose the floor which yields minimum number of trials.

x ==> Number of floors
n ==> Number of Eggs
eggDrop(n, k) ==> Minimum number of trials needed to find the critical
floor in worst case.

eggDrop(n, k) = 1 + min{max(eggDrop(n – 1, f– 1), eggDrop(n, k – f)), where f is in {1, 2, …, k}}

Runtinme complexity is: Exponential
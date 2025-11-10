# CMPS 2200 Assignment 3
## Answers

**Name:**Jordan Sztejman


Place all written answers from `assignment-03.md` here for easier grading.

1A: The greedy algorithm would be always choosing the largest coin that doesn't exceed the remaining ammount, then repeating this step until their is no more amount left.

1B:Greedy choice property:The greedy choice property says that we should pick the largest coin each time that doesn't exceed the remaining amount which we can label 2^k. This is because with powers of 2, we can make any possible amount. For this solution, we can only pick one of the 2^k coins because if we are able to pick two then greedy choice property would require us to pick 2^(k+1) instead which is contradictory to the original 2^k. If a solution didnt use the 2^k coin then it would be suboptimal as every single denomination below 2^k is exactly one less than 2^k. This means that picking the 2^k coin is always optimal. 

Optimal substructure property: The optimal substructure is that after using the 2^k coin, we have to find the remaining coins to use. If the substrutue is not opitmal then the original solution is not optimal for the solution which contradicts the fact that our first solution to the first coin was optimal. This means that optimal soltuions must have optimal substrucutres.

1C: The work of this algorithm is W(n)= O(log(n)) as we pick log(n) coins at most. The span of the alogorithm is S(n)= O(log(n)) as parallelization is not available because we need to take into account that we can not pick the next coin until we know what the coin before it is.

2A: A counter example that goes against the greedy algorithm is if I have denominations of [1,5,6] and an amount of 10. Greedy would pick the biggest coin and then pick four 1, or 6 + 1 + 1 + 1 + 1 =10. This is not optimal, picking two 5 coins is optimal. The optimal solution picks 2 coins, while greedy picks five.

2B:If we use a coin with a value "V" with an amount of "A", then the remaining solutions must be optimal for (A-V). Assuming we have an optimal solution using coin "V", then we find the amount of coin that it takes to find the amount(A-V). If this solution is not optimal and there is a better way to use the coins in order to have less coins then the whole solution is not optimal. The optimal solution for the amount "A" must include the the optimal solution for the amount (A-V).

2C:I would use a bottomup approach, where I would create a table of size n+1, n is the amount, and would find the minimum number of coins for each amount on the table. Then I would try to find if using smaller denominations would lead to a more optimized solution. For each denomination that doesn't exceed the current amount that I am working with, I would then check how many of that denomination would be used in the current amount. I would repeat this for all denominations and then would store the values that account to the lowest number of coins. The work of this solution would be W(n) = O(n*d), d is the number of denominations. The span of this solution would be S(n) = O(n) as some parallelization is possible when counting denominations.
[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/IF3rQO50)
# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

## Answer & Reasoning

Left Most Approach Good Pivot Probability: $\frac{1}{2}$ or 50%

For the median-of-three approach, there are 4 scenarios where we observe three elements and get a good pivot value:
1) Good Pivot, Good Pivot, Good Pivot (1 possible ordering)
2) Too small, Good Pivot, Good Pivot (3 possible orderings)
3) Too big, Good Pivot, Good Pivot (3 possible orderings)
4) Too small, Too big, Good Pivot (6 possible orderings)

And from the slides, we also know the probability of a random element being a good pivot is 1/2, the probability of a random element being too small is 1/4, and the probability of a random element being too big is 1/4.

So the probabilty of picking a good pivot value is:
$1(\frac{1}{2})(\frac{1}{2})(\frac{1}{2}) + 6(\frac{1}{4})(\frac{1}{2})(\frac{1}{4}) + 3(\frac{1}{2})(\frac{1}{4})(\frac{1}{2}) + 3(\frac{1}{2})(\frac{1}{4})(\frac{1}{2}) = 0.6875$  

That means our chances of picking a good pivot are 68.75%. Clearly we can tell that the median-of-three approach is more likely to pick a good pivot value, as it has a 68.75% chance of picking a good pivot value whereas the left-most approach only has a 50% chance of picking a good pivot value.
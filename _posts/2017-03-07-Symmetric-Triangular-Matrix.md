---
layout: post
title: Symmetric Triangular Matrix
---
## Introduction
If you have worked with graphs you've probably worked with an adjacency matrix. But if your graph is undirected, you can notice that the element `[i][j] = [j][i]`. Something similar happens when doing DFA Minimization. Unfortunately, this way we are "wasting" half of the memory and it doesn't sound good.

So what we would like to have is a data structure that works exactly the same but using half of the memory. We can do it easily just with a bit of calculus. By the way, in a graph we don't usually need the diagonal but in my example I'm going to consider it to make it simpler.

## Lower and Upper
First of all we are going to use a linear array to keep a fast access time and we will calculate the position manually. The triangular matrix can be lower or upper triangular:

<img src="https://fylux.github.io/public/img/TMatrix.jpg" width="48">

We are going to use the lower triangular and I'll tell you why later.

The size of the array instead of `N*N` will be:
$$
1 + 2 + 3 + ... + N = \frac{(N^2+N)}{2}
$$
an arithmetic progression, isn't it?

Now to obtain the position `(i,j)` in the matrix, we will do the following:

Because it is lower triangular, if j is greater than `i`, then `i=j` and `j=i`.
So the position in the linear array is:

$$
position = \frac{i^2+i}{2} + j
$$

It doesn't require much explanation. Essentially it calculates the corresponding i position using the arithmetic progression and then we add j.

If you had chosen an upper triangular matrix, the formula would be a little more complex because you are need to calculate something like `n + n-1 + n-2...n-i` and frankly, I prefer to keep things simple.


## Probably the best option
I just want to add that using half of the memory is a great advantage. The only disadvantage of this matrix is that it may have a very little overhead because of using a function to calculate the position. Definitely, it will be damn little the time used in calculus but if the bottleneck of your code is in array indexing and you don't care about using double of memory for the matrix you may want to see if you obtain any advantage using a common adjacency matrix. 

## Implementation
I've developed a simple implementation in C++ to play with it.
https://github.com/fylux/TriangularMatrix
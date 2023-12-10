# CMPS 2200 Assignment 5
## Answers

**Name:**Ethan Schaferkotter






- **1a.**

Where d is the number of children a node has and n is the number of nodes in the heap
The maximum depth of a d-ary heap is log_d(n(d-1)+1)

- **1b.**

Work done by delete-min would be O(d*log_d(n)) since the work in a binary heap is O(logn), this in context of the d-ary tree times the amount of times a swap needs to be made, d times. The work done by insert is also O(log_d(n))

- **1c.**

The work done by a Djikstra's algorithim on a d-ary heap would be delete-min + insert
Work for delete-min would take into account the number of nodes, so O(d(log_d(n))))
Work for insert would be O(log_d(n))
Total work would be O(d(log_d(|E|))) with every edge in the heap accounted for

- **1d.**

To get O(|E|), we can get that by solving for d when dlog_d|E| = |E|
Therefore the optimal value for d is |E|

- **2a.**

when k = 0

APSP(0,0,0) = 0 / ASPS(1,0,0) = -2 / APSP(2,0,0) = 2 / APSP(0,1,0) = -2 / APSP(0,2,0) = 2 / APSP(1,1,0) = 0 / APSP(1,2,0) = 1 / APSP(2,1,0) = 1 / APSP(2,2,0) = 0

when k = 1

APSP(0,0,1) = 0 / APSP(1,0,1) = -2 / APSP(2,0,1) = -1 / APSP(0,1,1) = -2 / APSP(0,2,1) = -1 / APSP(1,1,1) = 0 / APSP(1,2,1) = 1 / APSP(2,1,1) = 1 / APSP(2,2,1) = 0

when k = 2

APSP(0,0,2) = 0 / APSP(1,0,2) = -2 / APSP(2,0,2) = -1 / APSP(0,1,2) = -2 / APSP(0,2,2) = -1 / APSP(1,1,2) = 0 / APSP(1,2,2) = 1 / APSP(2,0,2) = -1 / APSP(2,1,2) = 1 / APSP(2,2,2) = 0

- **2b.**

APSP(i,j,1) and APSP(i,j,2) have the same solutions. The extra vertex does nothing to shorten the paths.
APSP(i,j,2) = APSP(i,j,1)

- **2c.**

APSP(i,j,k) = min(APSP(i,j,k-1), APSP(i,k,k-1) + APSP(k,j,k-1)) - non-inclusion of point k versus inclusion of point k as an intermediate

- **2d.**

In a graph with n vertices, i j and k can all range from 0 to n
Therefore, the resulting work would be n * n * n or n^3
O(n^3)

- **2e.**

Generally Johnson's algorithm is worse since it's work is only O(V^3).
To make our algorithm preferable, the number of edges has to be low in proportion to the number of vertexes.


- **3a.**

No, a solution to a MST problem is not guaranteed to be a solution to the MMET. The MST algorithm does not inherently minimize the maximum weights as it uses a greedy basis to make it's selection.

- **3b.**

The MST would still need to be computed. Afterward, you would have to identify what edges are not part of the MST. You could iterate through these edges and add it to the MST to create a new tree, and then find the new tree with the minimum total weight.

- **3c.**

The work for the algorithm would be O((E)(log(V))), since we're already doing MST and the loop to iterate over the edges is negligible.
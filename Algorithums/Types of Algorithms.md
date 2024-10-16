- Sorting 
- Searching
- Graph 
- backtracking algorithm
- Recursive algorithm

![](https://www.bigocheatsheet.com/img/big-o-cheat-sheet-poster.png)
# Sorting Algorithms
**8 types of sorting algorithms are there,**
1. insertion 
2. selection
3. Bubble 
4. Shell
5. Merge
6. Heap
7. Quick
8. Quick3
## Bubble Sort
Bubble sort is a simple sorting algorithm that repeatedly steps through the array, element by element, comparing the current element with the one after it, swapping their values if the format is larger than the latter.
>big-o time complexity => O(n^2)
## Insertion Sort
Insertion Sort is a simple sorting algorithm that builds the final sorted array one element at a time.
> big-o time complexity => O(n)
## Merge sort
Merge Sort is an efficient, stable, and comparison-based divide and conquer sorting algorithm, and its recursive(functions call itself). It divides the input array into halves, calls itself for the two halves, sorting them and then merges the two sorted halves.
> big-o time complexity => O(n log n)

# Searching Algorithms
## Linear search
Each element is checked in sequence until you find what you're looking for or the list ends,If the current element equals what we're looking for(x), return it
> big-o time complexity => O(n)
```python
def linear_search(arr, x):
	for i in range(len(arr)):
		if arr[i] == x:
			return i
	return -1
```
# Graph Algorithms
Graph algorithms are a set of instructions used to solve problems related to graph theory, where data is represented as collections of nodes connected by edges. like trees.

## Depth-First Search
Depth-first search is an algorithm for traversing or searching tree or graph data structures, the algorithm starts at the root mode and explores as far as possible along each branch before backtracking.
## Breadth-First Search
BFS is a layer-by-layer approach, casting a wide net form your starting pint and gradually widening it.

## Dijikstra's Algorithm
Dijkstra's algorithm finds the shortest path between a given node all other nodes in a graph using the weights of the edges to find the path that minimizes the total weight between the source node and all other nodes.

## A* Algorithm
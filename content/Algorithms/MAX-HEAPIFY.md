*Inputs:* an array $A$ with the *heapSize* attribute and an index $i$ into the array.  

*When called:*  It is assumed that the binary tree's rooted at $LEFT(i)$ and $RIGHT(i)$ are max-heaps, but that $A[i]$ might be smaller than it's children, thus violating the max-heap property.  

MAX-HEAPIFY lets the value of $A[i]$ *"float down"* in the max-heap so that the subtree rooted at index $i$ obeys the max-heap property.  

You basically just want to find the largest number out of the $A[LEFTCHILD(i)]$, $A[RIGHTCHILD(i)]$  and $A[i]$.  Then if either of the children's values are larger then $A[i]$ you want to swap the largest with $A[i]$ and recursively call MAX-HEAPIFY on the index where the largest value was before the swap.  


```python
def MAX_HEAPIFY(A, i):
	l = LEFT(i)
	r = RIGHT(i)
	if l <= A.heapSize() and A[l] > A[i]:
		largest = l
	else:
		largest = i
	if r <= A.heapSize() and A[r] >  A[largest]:
		largest = r
	if largest != i:
		value = A[i]
		A[i] = A[largest]
		A[largest] = value
		MAX_HEAPIFY(A,largest)
```

![[Pasted image 20240923121246.png]]

# Time Complexity 

$\Theta (1)$ to compute the relationship between $A[i]$ and the two children plus the time it takes to run MAX_HEAPIFY on the subtree (the recursion).  The children's subtrees each have size at most $2n/3$ so the run time of MAX_HEAPIFY is:

$T(n) \leq T(\frac{2n}{3}) + \Theta (1)$ 

This is an example of case 2 of the [[Algorithms/Master Theorem|Master Theorem]] so the solution is $T(n) = O(lgn)$ 
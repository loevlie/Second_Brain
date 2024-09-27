
## Minimum

It takes an upper bound and lower bound of $n - 1$ comparisons to obtain a minimum of a set of $n$ elements.  

```python
def minimum(A):
	n = len(A)
	for i in range(1, n):
		if min > A[i]:
			return A[i]
	return min
```

## Simultaneous min and max

We can obtain a min and max in $\Theta (n)$ comparisons.  We could just find them separately which would be $2n - 2$ comparisons and be $\Theta (n)$.  It's possible to find the min and the max in at most $3 \times floor(n/2)$ comparisons.  The trick is to process the input in pairs.  First compare the pair with each other, then compare the smaller number with the min and the larger with the max.  A cost of 3 comparisons for every 2 elements.  

### Initializing the min / max

**If $n$ is odd** - Set both the min and max to the first element. 

**If $n$ is odd** - Compare the first two elements and set the lower to the min and the higher to the max.  

Either way you still have $3 floor(n/2)$ comparisons.  If n is even, you have 1 initial comparison followed by another $\frac{3(n-2)}{2}$ comparisons, for a total of $\frac{3n}{2} - 2$.  
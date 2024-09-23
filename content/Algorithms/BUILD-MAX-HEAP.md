
Converts an array $A[1:n]$ into a max-heap by calling [[MAX-HEAPIFY]] in a bottom-up manner.  

```python
def build_max_heap(A, n):
	A.heapSize = n
	array = np.arange(1,np.floor(n/2))[::-1]
	for i in array:
		MAX_HEAPIFY(A, i)
```

![[Pasted image 20240923124939.png]]

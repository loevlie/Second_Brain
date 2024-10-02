Sorting algorithms rearrange arrays.  Stable sorting algorithms **do not permute** equal entries.  

![[Pasted image 20240928081734.png]]

>[!info] 
>Example:  If you have two columns (name and gpa) and the "key" is the GPA.  You want to sort by GPA but when you have equal GPA values you want to keep the names in alphabetical order (they are currently in alphabetical order).  You would want a stable sorting algorithm for this use case.  

## Partition (why is it not stable?)

## Example

**Input Array:** $[4a,2,4b,3,4c,1]$

Partition code:

```python
def partition(A,p=-1):
	# Assuming we just choose p to equal the last element in the array
	partition = A[p] # This is 1
	i = -1 # Starts before the array index values because it gets incremented
	for j in range(0, len(A)-1):
		# None of the elements are less than 1 in our example
		if A[j] <= partition: 
			i += 1
			value = A[j]
			A[j] = A[i]
			A[i] = value
	value = A[-1]
	A[-1] = A[i+1]
	A[i+1] = value
	return i+1, A
```

![[Screenshot 2024-10-02 at 11.24.17 AM.png]]

*Notice the 4 at the end was initially at the beginning of the array*

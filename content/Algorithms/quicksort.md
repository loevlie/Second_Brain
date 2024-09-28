## Worst Case Time Complexity 

### When the partition is unbalanced

![[Screenshot 2024-09-27 at 5.47.18 PM.png]]
You can say that $T(n) \leq T(n+1)$ So you can make the above $T(n) + n$ 
### When it is Balanced

$T(n) \leq T(n/4) + T(3n/4) + n$

## Expected Time (average)?

If the Partition is balanced in 50% of the cases:

$T(n) \leq \frac{1}{2} (T(n) + n) +  \frac{1}{2} (T(\frac{n}{4}) +T(\frac{3n}{4}) + n )$

This is equivalent to:

$\frac{1}{2} T(n) \leq \frac{1}{2}(T(\frac{n}{4}) +T(\frac{3n}{4})) + n$

$T(n) \leq T(\frac{n}{4}) +T(\frac{3n}{4}) + 2n$ = $\Theta (nlogn)$

**Randomized-quicksort is the same as the average case** - 1/2 chance of being balanced with randomly chosen pivot.  



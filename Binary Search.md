---
title: Binary Search
---
The binary search algorithm allows for quicker search by splitting the search interval into two. Because of this, it runs in $O(\log n)$.

Here we use binary search to find the value $x$ in the array $a$:

```cpp
int l = 0, r = n-1;
while (l <= r) {
	int mid = l+(r-l)/2;
	if (a[mid] == x) {
		// ...
	}
	if (a[mid] > x) r = mid-1;
	else l = mid+1;
}
```

More generally, it can be used to identify the position where the value of a boolean function changes. Let $f : \{0, 1, ..., n-1\} \to \{0, 1\}$ be a **monotonic** function (i.e., $f(0) \le f(1) \le ... \le f(n-1)$.) We can use binary search to find the "transition point" where $f$ goes from $0$ to $1$. In fact: if we look at the current position and the value is $0$, because of the monotonicity of the function we know that the transition point must be to the right; if we look at the current position and the value is $1$, because of the monotonicity of the function we know that the transition point must be to the left.

```cpp
int l = 0, r = n-1;
while (l <= r) {
	int mid = l+(r-l)/2;
	if (f(mid)) r = mid-1;
	else l = mid+1;
}
```

At the end, `l` is going to point to the first position where $f$ is $1$.

It can also be used to find the maximum value of a **unimodal** function (a function that is first increasing and then decreasing.) Basically we want to find the point $k$ such that $f(x) < f(x+1)$ when $x < k$ and $f(x) > f(x+1)$ when $x \ge k$.

```cpp
int l = 0, r = n-1;
while (l < r) {
	int mid = l+(r-l)/2;
	if (f(mid) < f(mid+1)) l = mid+1;
	else r = mid;
}
```

C++ has built-in functions to perform binary search, namely `lower_bound` and `upper_bound`.
- `lower_bound` returns a pointer to the first element whose value is at least $x$.
- `upper_bound` returns a pointer to the first element whose value is greater than $x$.

Problems:
- [Billion Players Game](https://codeforces.com/contest/2157/problem/D)

References:
- [CPH](https://usaco.guide/CPH.pdf#section.3.3)
- [cp-algorithms](https://cp-algorithms.com/num_methods/binary_search.html)
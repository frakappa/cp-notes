Given an array of $n$ elements, we want to find, for each position, the nearest position to its left having a smaller value.

The idea is that we can go through the array from left to right keeping a [[Monotonic Stack|monotonic stack]].

```cpp
vector<int> st;
for (int i = 0; i < n; i++) {
	int j = -1;
	while (!st.empty()) {
		j = st.back();
		if (a[j] < a[i]) break;
		st.pop_back();
	}
	st.push_back(i);
	if (j == -1 || a[j] >= a[i]) {
		// we have not found a smaller element to the left
	} else {
		// we have found a smaller element to the left
	}
}
```

Notice that we can safely remove values from the stack if the value at the current position is smaller. This is because, for the values at the subsequent positions, the element at the current position will always appear as a closer smaller value before any of the elements we have removed.

The time complexity of this algorithm is $O(n)$. Intuitively, each element is added and removed from the stack at most once, so, overall, the number of stack operations in the loop is constant.

Problems:
- [Nearest Smaller Values](https://cses.fi/problemset/task/1645/)
- [Nearest Taller](https://atcoder.jp/contests/abc433/tasks/abc433_b)
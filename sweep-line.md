---
title: Sweep Line
---
# Sweep Line

The _sweep line_ (or _event processing_) technique consists in compressing a dynamic process into a sorted list of "events" and then processing these events as we "sweep" from left to right.

It's particularly useful for [geometry](geometry.md) problems and is often able to turn $O(n \cdot m)$ algorithms into $O((n + m) \log n)$ algorithms.

Consider the problem linked at the bottom of the page. We identify two types of events: an event that occurs when the price exceeds $a_i$ and the customer leaves a negative review; and an event that occurs when the price exceeds $b_i$ and the customer doesn't buy the tree anymore but also doesn't leave a negative review. At the beginning every customer buys the tree, but as we increase the price and more event occurs, some customers will leave negative reviews and others won't buy the tree anymore. We keep track of the best outcome for each price.

```cpp
// For each price, we keep a list of events
map<int, vector<int>> ev;
for (int i = 0; i < n; i++) {
	// An event of type 1 indicates that, when the price exceeds a[i],
	// the customer will leave a negative review
	ev[a[i]].pb(1);
	// An event of type 2 indicates that, when the price exceeds b[i],
	// the customer will not buy the tree anymore
	ev[b[i]].pb(2);
}

ll ans = 0;

// At the start, every customer will buy the tree without leaveing a negative review
ll cnt = n, neg = 0;
for (auto [k, v] : ev) {
	// We update the answer if we have a valid configuration
	// This happends BEFORE we process the events,
	// as an event occurs when we EXCEED the price
	if (neg <= k) ans = max(ans, (ll)k*cnt);
	
	// We update the events based on the type
	for (auto e : v) {
		if (e == 1) neg++;
		else cnt--, neg--;
	}
}
```

Problems:
- [Best Price](https://codeforces.com/problemset/problem/2051/E)
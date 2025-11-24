---
title: Number of Divisors
---
# Number of Divisors

The _divisor function_ counts the number of divisors of an integer.

[Wigert](https://en.wikipedia.org/wiki/Carl_Severin_Wigert) showed that:

$$
\limsup_{n \to \infty} \frac{\log d(n)}{\log n / \log \log n} = \log 2
$$

Basically, the number of divisors of $n$, written $d(n)$, is very small compared to $n$.

Its worst case is roughly:

$$
d(n) \lesssim \exp(O(\frac{\log n}{\log \log n}))
$$

In practice, $d(n)$ is at most a few hundreds for $n \le 2 \cdot 10^5$ and algorithms with complexity like $O(n \cdot d(n))$ are usually safe.

Problems:
- [Nearly Shortest Repeating Substring](https://codeforces.com/problemset/problem/1950/E)

References:
- [Divisor function](https://en.wikipedia.org/wiki/Divisor_function)
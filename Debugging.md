- Is [[IO]] correct?
- Check edge cases.
- Read the problem statement again.
- Read the code again.
- Check shadowed/unused/uninitialized variables (`-Wall` and `-Wshadow` can help.)
- Check mutable variables.
- Check undefined behavior.
	- Uninitialized variables.
	- Not returning from non-`void` functions.
	- Array out-of-bounds.
	- [[Integers|Integer]] overflow.
- Add assertions.
- Prove the solution.

It may be useful to check the value of certain variables/expressions. The following macro prints the given expression along with its value:

```cpp
#define dbg(x) cout << #x << " = " << (x) << "\n";
```

It may also be useful to use `assert(condition)`, to assert the a condition `condition` holds. If it doesn't, the program is terminated with a runtime error.

References:
- [USACO guide](https://usaco.guide/general/debugging-checklist)
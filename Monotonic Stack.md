A monotonic stack is a stack that maintains its elements in a fixed order (either increasing or decreasing.) Whenever we want to push a new element, we compare it to the top of the stack: if the order is violated, elements are popped until the property is restored, and then the new element is pushed.

This way, the stack stays ordered and, since each element is pushed and popped at most once, the overall algorithm runs in linear time.

A monotonic stack can be used to solve problems such as finding the [nearest smaller value](Nearest%20Smaller%20Value.md) in linear time.

References:
- [GFG](https://www.geeksforgeeks.org/dsa/introduction-to-monotonic-stack-2/)
---
title: Greedy Algorithms
---
# Greedy Algorithms

> A greedy algorithm constructs a solution to the problem by always making the choice that looks best at the moment. A greedy algorithm never takes back its choices, but directly construct the final solution. For this reason, greedy algorithms are usually very efficient.

Greedy does not refer to a single algorithm, but rather to a class of algorithms, or, more generally, to a way of thinking.

It is often difficult to argue that greedy algorithms work.

In general, greedy algorithms are correct when:
- A global solution can be constructed by making a locally optimal choice.
- After making a greedy choice, the remaining problem is still optimal.

Common ways of proving that a greedy algorithms works include:
- Showing that an optimal solution can be transformed into a greedy one.
- Showing that after each step, the greedy solution is at least as good as any other solution.

On the other hand, proving that a greedy algorithm does NOT work usually involves providing a counterexample.

Common greedy patterns include:
- Sorting and taking in order.
- Taking the best immediate gain.
- Maintaining the best candidate dynamically (e.g., with a priority queue.)

For example, let us consider a problem where we are given $n$ tasks with durations and deadlines. For each task, we earn $d - x$ points where $d$ is the task's deadline and $x$ is the moment we finish the task. Our job is to choose an order to perform the tasks. What is the largest possible total score we can obtain?

For example, suppose that the tasks are as follows:

| task | duration | deadline |
| ---- | -------- | -------- |
| $A$  | $4$      | $2$      |
| $B$  | $3$      | $5$      |
| $C$  | $2$      | $7$      |
| $D$  | $4$      | $5$      |

In this case, an optimal schedule for the task is as follows: $C$, $B$, $A$, $D$. In this solution, $C$ yields $5$ points, $B$ yields $0$ points, $A$ yields $-7$ points and $D$ yields $-8$ points. So the total score is $-10$.

The optimal strategy is to perform the tasks in order _sorted by their durations_. One way we can argue this works is that if we were to perform task $X$ with duration $a$ before task $Y$ with duration $b$ where $a > b$, we could have simply gotten a better outcome by swapping the two tasks. In fact, if we swap the two tasks, the total score increases by $a - b > 0$  points.

Resources:
- [CPH](https://usaco.guide/CPH.pdf#chapter.6)
- [USACO Guide](https://usaco.guide/bronze/intro-greedy)
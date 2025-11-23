The standard way to do IO is to use `cin` and `cout`. `cin` reads whitespace-separated data, including tabs (`\t`) and newlines (`\n`), from standard input.

Some judges (such as USACO) require doing IO with files. The easiest way to do this is using `freopen`:

```cpp
freopen("file.in", "r", stdin);
freopen("file.out", "w", stdout);
```

which allows to write code using standard streams.

Sometimes IO is the bottleneck. Adding the following can make IO more efficient:

```cpp
ios::sync_with_stdio(0);
cin.tie(0);
```

Also, `\n` works faster than `endl`, because `endl` always causes a flush operation.

Sometimes you want to read an entire line from the input, possibly containing whitespaces. This can be done with `getline`:

```cpp
string s;
getline(cin, s);
```

If the amount of data is unknown, the following loop is useful:

```cpp
while (cin >> x) {
	// ...
}
```
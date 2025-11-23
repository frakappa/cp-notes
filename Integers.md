The most common integer type is `int`, which is a **32-bit** type with a value range of $-2^{31} ... 2^{31}-1$ (or about $-2 \cdot 10^{9} ... 2 \cdot 10^{9}$).

If `int` is too small, the **64-bit** type `long long` can be used. It has a value range of $-2^{63} ... 2^{63}-1$ (or about $-9 \cdot 10^{18} ... 9 \cdot 10^{18}$).

You can add `LL` to the end of a number to make it `long long` (e.g., `123456789123456789LL`). This in important in the case of really big constants.

Be careful with using `long long` where `int` is still used, it may lead to unexpected errors. You can convert from `int` to `long long` with `(long long)` (e.g., `(long long)x`, where `x` is an `int` variable.)

The g++ compiler also provides a **128-bit** integer type, `__int128_t`, but it's not available in all contest systems.

When working with really huge numbers, the problem may ask to give the output **modulo** a certain value, check [[modular arithmetic|Modular Arithmetic]].
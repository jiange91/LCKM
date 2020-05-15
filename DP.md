# Dynamic Programming is Sh*t

### Problem 278:

1. Normal euqation to obtain average
    ```
    (a+b) / 2
    ```
    might generate Overflow problem since we cannot guarantee that `(a+b)` would stay in the range, instead we can use 
    ```
    a + (b - a) / 2
    OR
    a/2 + b/2 + (a%2 + b%2)/2
    ```
    to prevent this issue

2. When using two pointers indicating former and rear limitations, if we want to quit the `while` process, let one of the pointer exceed the pivot.

    ```
    while (rear > former) {
        int m = former + (rear - former) / 2;
        if (isBadVersion(m)) rear = m;
        else former = m+1;
    }
    return rear;
    ```

### Problem 540

1. Find unique element in a list of even number of integers.
    ```
    k = nums[0];
    for (int i : nums[0])
        k ^= i;
    ```
    Bitwise `^` operator set bit to 1 if different, 0 otherwise.

2. Elegant use of `^`
    ```
    nums[i ^ 1];
    ```
    Get preceeding element if current index is odd number, otherwise get the rear one.
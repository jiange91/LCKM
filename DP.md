# Dynamic Programming is Sh*t

### 278:

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


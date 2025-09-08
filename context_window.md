
```python
list = [15, 6, 9, 12, 12, 7, 6, 6, 9]
```

* Generate Sublist
    ```python
    def generate_sublist(l,k=3,s=2):
        for i in range(0,len(l), s):
            for j in range(k):
                pass
            print(l[i:i+k])
    ```

* Result
    ```python
    [15, 6, 9]
    [9, 12, 12]
    [12, 7, 6]
    [6, 6, 9]
    [9]
    ```

* Get Max-Interval-Sum (Basic Algorithm)
    ```python
    def get_interval_sum(l,k=3):
        max_sum = 0
        for i in range(len(l)-k+1):
            current_max = 0
            for j in range(k):
                current_max = current_max + l[i+j]
            if current_max > max_sum:
                max_sum = current_max
        return max_sum
    ```

* Result
    ```python
    [33]
    ```
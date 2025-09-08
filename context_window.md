* Random List
    ```python
    import random as rd
    nums = [rd.randint(2,15) for _ in range(9)]
    nums = [15, 6, 9, 12, 12, 7, 6, 6, 9]
    nums = [4, 13, 7, 3, 8, 10, 9, 13, 9]
    ```


* Generate Sublist 
    ```python
    def generate_sublist(l,k=3):
        for i in range(len(l)):
            for j in range(k):
                pass
            print(l[i:i+k])
    ```


* Result
    ```python
    [4, 13, 7]
    [13, 7, 3]
    [7, 3, 8]
    [3, 8, 10]
    [8, 10, 9]
    [10, 9, 13]
    [9, 13, 9]
    [13, 9]
    [9]
    ```



* Generate Sublist with step
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




- Step = 1
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

    * Complexity
        ```python
            O(n^2)
        ```

    * Get Max-Interval-Sum (Moving window Algorithm)
        ```python
        def get_interval_sum(l,k=3):
            max_sum = current_sum = sum(l[:k])
            for i in range(k, len(l)):
                current_sum = current_sum - l[i-k] + l[i]
                if current_sum > max_sum:
                    max_sum = current_sum
            return max_sum
        ```

    * Complexity
        ```python
            O(n)
        ```





- Step > 1
    * Get Max-Interval-Sum (Basic Algorithm)
        ```python
        def get_interval_sum(l,k=3,s=2):
            max_sum = 0
            for i in range(0,len(l)-1,s):
                current_max = 0
                for j in range(k):
                    current_max = current_max + l[i+j]
                if current_max > max_sum:
                    max_sum = current_max
            return max_sum
        ```

    * Complexity
        ```python
            O(n^2)
        ```

    * Get Max-Interval-Sum (Moving window Algorithm)
        ```python
        def max_sum_with_slide(arr, k, slide):
            n = len(arr)
            if k > n or k <= 0 or slide <= 0:
                raise ValueError("Invalid window size or slide step")
        
            max_sum = float('-inf')
            best_window = []
        
            # Step through the array using the given slide
            for i in range(0, n - k + 1, slide):
                current_window = arr[i:i + k]
                current_sum = sum(current_window)
        
                if current_sum > max_sum:
                    max_sum = current_sum
                    best_window = current_window
        
            return max_sum, best_window
        ```

    * Complexity
        ```python
            O(n)
        ```

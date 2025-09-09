* Generate Subarray 
    ```python
    def generate_sublist(nums):
        c=0
        for i in range(len(nums)):
            for j in range(i+1,len(nums)+1):
                # Suppose nums = [1, 2, 3] and i = 0:
                # range(i+1, len(nums)+1) → range(1, 4) → generates 1, 2, 3
                # Without +1, range(1, 3) → generates 1, 2 (missing the last index)
                print(nums[i:j])
                c+=1
        return c
        ```
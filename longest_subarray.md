* Generate Subarray.

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



* Get the index of element. (Two Sum)

    ```python
    def two_sum(nums, target):
        num_map = {}  # to store value -> index
        for i, num in enumerate(nums):
            diff = target - num
            if diff in num_map:
                return [num_map[diff], i]
            num_map[num] = i
    ```

    - It use `hash map`, is a data structure that allows you to store key-value pairs.
    - In the `Two Sum` problem, we use a hash map (dictionary) to remember which numbers we've seen and at which index, so we can quickly check if the complement (target - current number) already exists. `O(n)`
    - Is dictionary and hash map is different or same in python ? 
    - Python's `dict` is its built-in implementation of a hash map. 
    - `hash map` -> `The underlying data structure (concept) that dict uses`



* Remove Duplicate and return unique element `in-place`.

    ```python
    def removeduplicate(l, val):
        k = 0                   # `k` is for the position from start, those value in list that does not match with given `val`.
        for i in range(len(l)): # iterate over the list for every element.
            if l[i] != val:     # if given position is not equal to value.
                l[k] = l[i]     # In list put the value of kth position with the next upcoming non matched value with `val` of list.
                k+=1            # If matched increment the value of k.
        return l

    l=[8, 3, 4, 9, 10, 5, 3, 7, 7, 10, 10, 4, 10, 7, 5]
    print(removeduplicate(l,val=10))  # [8, 3, 4, 9, 5, 3, 7, 7, 4, 7, 5, 4, 10, 7, 5]
    ```



* Remove repeted Element.

    ```python
    def remove_repeted_element(l):
        k=0                     # `k` is for the position from start, those value in list that does not match with `k`th position value.
        for i in range(len(l)): #  iterate over the list from this loop.
            if l[i] != l[k]:    #  cheak if `CurentPosition` value is not equal to `k`th position that is track of non-matching number.
                k+=1            #  Increment the `k`th position as we find the next non-matching number.
                l[k] = l[i]     #  update the value in list of `k`th position with new non-matching word.
        return l                # This is full in-place modification of list in O(n)

    l = [0,0,1,1,1,2,2,3,3,4]
    remove_repeted_element(l)   # [0, 1, 2, 3, 4, 2, 2, 3, 3, 4]
    ```



* Move Zeros.

    ```python
    class Solution:
        def moveZeroes(self, nums) -> None:
            """
            Do not return anything, modify nums in-place instead.
            """

            k = 0 
            for i in range(len(nums)):
                if nums[i] != 0:
                    nums[k] = nums[i]
                    k+=1

            for i in range(k, len(nums)):
                nums[i] = 0
            return nums
        
    print(Solution().moveZeroes(nums = [0,1,0,3,12]))
    ```




* Happy Number

    ```python
    Input: n = 19
    Output: true
    Explanation:
    12 + 92 = 82
    82 + 22 = 68
    62 + 82 = 100
    12 + 02 + 02 = 1
    ```


    ```python
    def get_next_value(n):
        return sum(int(i) **2 for i in str(n))

    def is_happyNumber(n):
        seen = set()
        while n != 1 and n not in seen:
            seen.add(n)
            n = get_next_value(n)
        print(seen)
        return n==1


    print(is_happyNumber(647))
    ```



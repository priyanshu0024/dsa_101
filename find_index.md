* Find the Index of the First Occurrence in a String.

    - Solution 1
        ```python
        # Returns the index of the first occurrence of 'needle' in 'haystack', or -1 if not found
        class Solution:
            def strStr(self, haystack: str, needle: str) -> int:
                s = len(haystack)
                p = len(needle)
                for i in range(s - p + 1):
                    if haystack[i:i+p] == needle:
                        return i
                return -1

        print(Solution().strStr(haystack = "adbutsad", needle = "sad"))
        ```

    - Solution 2
        ```python
        # Returns a list of all starting indices where 'needle' occurs in 'haystack'
        class Solution:
            def strStr(self, haystack: str, needle: str) -> int:
                l = []
                s = len(haystack)
                p = len(needle)
                for i in range(s-p+1):
                    matchded = True
                    j = 0
                    while j<p and matchded:
                        if haystack[i+j] != needle[j]:
                            matchded = False
                        j = j + 1
                    if matchded:
                        l.append(i)
                return l

        print(Solution().strStr(haystack = "sadbutsad", needle = "sad"))
        ```



* Longest Common Prefix

    ```python
    def longestCommonPrefix(strs):
        if not strs:
            return ""

        for i in range(len(strs[0])):
            char = strs[0][i]
            for s in strs[1:]:
                if i >= len(s) or s[i] != char:
                    return strs[0][:i]
        
        return strs[0]


    # print(longestCommonPrefix(["flower","flow","flight"]))
    s=["dog","racecar","car"]
    print(longestCommonPrefix(s)) # output : fl
    ```
* Valid Palindrome

    ```python
    def isPalindrome(s: str) -> bool:
        left, right = 0, len(s) - 1

        while left < right:
            # Move left pointer if not alphanumeric
            while left < right and not s[left].isalnum():
                left += 1
            # Move right pointer if not alphanumeric
            while left < right and not s[right].isalnum():
                right -= 1

            # Compare characters ignoring case
            if s[left].lower() != s[right].lower():
                return False

            left += 1
            right -= 1

        return True

    print(isPalindrome("A man, a plan, a canal: Panama"))
    ```

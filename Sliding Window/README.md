🚀 Sliding Window & Two Pointer - README

This document contains a summary + categorized list of classic sliding window / two pointer problems.
These patterns are essential for substring/subarray problems involving frequency, distinct counts, or constraints.

🔑 Key Ideas
🔹 Sliding Window

Maintain a window [l, r] over the array/string.

Expand r (right pointer) to include elements.

Shrink l (left pointer) when constraints break.

Use hashmap/frequency counter to track counts.

Best for substrings/subarrays involving conditions.

🔹 Two Pointer

Two indices move through the array (can be same direction or opposite).

Common in sorted arrays / special conditions.

Often reduces brute force O(n²) → O(n).

📚 Problems
1. Binary Subarrays With Sum (LeetCode 930)

Type: Prefix sum + Hashmap (variation of sliding window).

Idea: Count subarrays with sum = S using prefix sums.

Complexity: O(n)

2. Count Number of Nice Subarrays (LeetCode 1248)

Type: Sliding window (count subarrays with k odd numbers).

Trick:
#subarrays with exactly k = atMost(k) - atMost(k-1)

Complexity: O(n)

3. Fruit Into Baskets (LeetCode 904)

Type: Longest subarray with ≤ 2 distinct elements.

Method: Standard sliding window with map.

Complexity: O(n)

4. Longest Repeating Character Replacement (LeetCode 424)

Type: Sliding window with frequency count.

Idea: Keep track of maxFreq.
If (windowSize - maxFreq) > k, shrink window.

Complexity: O(n)

5. Longest Substring Without Repeating Characters (LeetCode 3)

Type: Sliding window + set/map.

Idea: Expand until repeat, then shrink left.

Complexity: O(n)

6. Max Consecutive Ones III (LeetCode 1004)

Type: Sliding window (longest subarray with ≤ k zeros).

Idea: Count zeros, shrink if count > k.

Complexity: O(n)

7. Maximum Points You Can Obtain from Cards (LeetCode 1423)

Type: Two pointer prefix/suffix.

Idea: Equivalent to removing a middle subarray of size n-k.
Find min sum window, subtract from total.

Complexity: O(n)

8. Minimum Window Subsequence (LeetCode 727)

Type: Two pointer + scanning.

Brute: Try every start (O(n²)).

Optimal: Forward scan for t, backward shrink for min window.

Complexity: O(n*m)

9. Minimum Window Substring (LeetCode 76)

Type: Classic sliding window.

Method: Expand r until valid, shrink l to minimize.

Complexity: O(n)

10. Number of Substrings Containing All Three Characters (LeetCode 1358)

Type: Sliding window with atMost.

Trick: count = atMost(n) - atMost(n-1)

Complexity: O(n)

11. Subarrays with K Different Integers (LeetCode 992)

Type: Sliding window.

Trick: exactlyK = atMost(K) - atMost(K-1)

Complexity: O(n)

12. Substring with At Most K Distinct Characters (LeetCode 340)

Type: Sliding window with map.

Idea: Track distinct counts. If > k, shrink window.

Complexity: O(n)

⚡ Common Patterns

Longest Window Problems → Keep expanding until constraint fails, then shrink.
Examples:

Longest Substring Without Repeat

Max Consecutive Ones III

Fruit Into Baskets

Minimum Window Problems → Expand to satisfy, then shrink to minimize.
Examples:

Minimum Window Substring

Minimum Window Subsequence

Counting Subarrays/Substrings → Use atMost(k) - atMost(k-1) trick.
Examples:

Nice Subarrays

Subarrays with K Distinct

Substrings with 3 characters

Prefix/Suffix Optimization → Sometimes easier than window.
Example: Maximum Points from Cards

📌 Time Complexities Overview

Most sliding window: O(n)

Subsequence (2 pointers): O(n*m)

Prefix/suffix trick: O(n)

📌 Longest Substring Without Repeating Characters

Problem:
Given a string s, find the length of the longest substring without repeating characters.

✅ Brute Force (O(N²))

Idea:
Generate all substrings using two loops.
For each substring, check if it has all unique characters (using set).

Code Snippet (C++):

int solve(string str) {
    int maxans = 0;
    for (int i = 0; i < str.length(); i++) {
        unordered_set<int> st;
        for (int j = i; j < str.length(); j++) {
            if (st.find(str[j]) != st.end()) break;
            st.insert(str[j]);
            maxans = max(maxans, j - i + 1);
        }
    }
    return maxans;
}


Time: O(N²)

Space: O(N)

⚡ Optimized Approach 1 (Sliding Window, O(2N))

Idea:
Maintain two pointers l and r.
Expand r while elements are unique.
If duplicate → move l forward & erase duplicates.

Code Snippet (C++):

int solve(string str) {
    unordered_set<int> st;
    int l = 0, maxans = 0;
    for (int r = 0; r < str.length(); r++) {
        while (st.find(str[r]) != st.end()) {
            st.erase(str[l]);
            l++;
        }
        st.insert(str[r]);
        maxans = max(maxans, r - l + 1);
    }
    return maxans;
}


Time: O(2N)

Space: O(N)

🚀 Optimized Approach 2 (Sliding Window + Map, O(N))

Idea:
Use a map/vector to store the last index of characters.
If duplicate found, move l to max(l, lastIndex + 1).
Always update last seen index of current char.

Code Snippet (C++):

int lengthOfLongestSubstring(string s) {
    vector<int> mpp(256, -1);
    int l = 0, maxlen = 0;
    for (int r = 0; r < s.size(); r++) {
        if (mpp[s[r]] != -1)
            l = max(mpp[s[r]] + 1, l);
        mpp[s[r]] = r;
        maxlen = max(maxlen, r - l + 1);
    }
    return maxlen;
}


Time: O(N)

Space: O(256)

🏆 Best Approach: Optimized Approach 2

✅ Runs in linear time.
✅ Uses direct indexing (fast lookup).

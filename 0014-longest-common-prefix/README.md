# Longest Common Prefix

## Problem

Given an array of strings, find the longest common prefix shared by all strings.

Return an empty string `""` if there is no common prefix.

### Example 1

```text
Input: ["flower", "flow", "flight"]
Output: "fl"
```

### Example 2

```text
Input: ["dog", "racecar", "car"]
Output: ""
```

## Approach

Use the first string as the reference.

For each character in the first string:

1. Compare it with the character at the same index in every other string.
2. If a string is shorter or the characters do not match, return the prefix found so far.
3. If all characters of the first string match, return the complete first string.

## C++ Solution

```cpp
class Solution {
public:
    string longestCommonPrefix(vector<string>& strs) {
        for (int i = 0; i < strs[0].size(); i++) {
            char currentChar = strs[0][i];

            for (int j = 1; j < strs.size(); j++) {
                if (i >= strs[j].size() || strs[j][i] != currentChar) {
                    return strs[0].substr(0, i);
                }
            }
        }

        return strs[0];
    }
};
```

## Complexity

* **Time Complexity:** `O(n × m)`
* **Space Complexity:** `O(1)`

Where:

* `n` is the number of strings.
* `m` is the length of the shortest common prefix checked.

## LeetCode Problem

Problem 14: Longest Common Prefix

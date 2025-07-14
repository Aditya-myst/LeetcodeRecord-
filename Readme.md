
✅ Updated README.md
markdown
Copy
Edit
# 📅 Date: 14-07-2025

# 🚀 LeetCode Preparation Notes

A curated list of important and tricky **LeetCode problems** I’ve solved, with concise notes and key learnings.  
This helps me track progress, revise concepts faster, and prepare for coding interviews effectively.

---

## 📚 Table of Contents

- [✅ 1. Add Binary – LeetCode 67](#-1-add-binary--leetcode-67)
- [✅ 2. 4Sum – LeetCode 18](#-2-4sum--leetcode-18)
- [✅ 3. 01 Matrix – LeetCode 542](#-3-01-matrix--leetcode-542)
- [🛠️ More Coming Soon...](#️-more-coming-soon)

---

## ✅ 1. Add Binary – [LeetCode 67](https://leetcode.com/problems/add-binary/)

**Problem:**  
Add two binary strings and return their sum (as a binary string).

**Key Learnings:**
- Use `size() - 1` to access the last index of a string.
- Add digits from right to left using a carry.
- Build result by **prepending** to the result string.

```cpp
result = to_string(sum % 2) + result;
Code Snippet:

cpp
Copy
Edit
for (int i = a.size() - 1, j = b.size() - 1; i >= 0 || j >= 0 || carry; i--, j--) {
    int sum = carry;
    if (i >= 0) sum += a[i] - '0';
    if (j >= 0) sum += b[j] - '0';
    result = to_string(sum % 2) + result;
    carry = sum / 2;
}
```

✅ 2. 4Sum – LeetCode 18
Problem:
Find all unique quadruplets in the array that sum up to the target.

Key Learnings:

Use sorting + two pointers strategy.

Fix the first two numbers using indices i and j.

Use two pointers left and right to find remaining two.

Skip duplicates at every level to avoid repeated results.

Concept:

Fix i, then j, then use two-pointer method for left and right.

Skip duplicate values at each stage:

cpp
while (i > 0 && nums[i] == nums[i - 1]) i++; // etc.
Handles:

Negative numbers

Overflow (use long long)

Duplicates (clean result)

✅ 3. 01 Matrix – LeetCode 542
Problem:
Given a binary matrix, return the distance of each cell with 1 to its nearest 0.

Key Learnings:

To initialize a 2D matrix with default value:

cpp
vector<vector<int>> dist(n, vector<int>(m, 1e5)); // large number
Use Two-Pass Dynamic Programming (no BFS/queue):

Pass 1: Top-Left ➝ Bottom-Right

cpp
Copy
Edit
if (i > 0)    dist[i][j] = min(dist[i][j], dist[i - 1][j] + 1);
if (j > 0)    dist[i][j] = min(dist[i][j], dist[i][j - 1] + 1);
Pass 2: Bottom-Right ➝ Top-Left

cpp
Copy
Edit
if (i < n - 1)  dist[i][j] = min(dist[i][j], dist[i + 1][j] + 1);
if (j < m - 1)  dist[i][j] = min(dist[i][j], dist[i][j + 1] + 1);
Set dist[i][j] = 0 where mat[i][j] == 0 before starting.

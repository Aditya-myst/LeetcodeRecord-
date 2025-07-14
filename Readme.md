
````markdown
# 🚀 LeetCode Preparation Notes

A curated list of important and tricky **LeetCode problems** I’ve solved, with concise notes and key learnings.  
This helps me track my progress, revise concepts faster, and prepare for coding interviews efficiently.

---

## 📚 Table of Contents

- [✅ Add Binary - LeetCode 67](#-1-add-binary---leetcode-67)
- [✅ 01 Matrix - LeetCode 542](#-2-01-matrix---leetcode-542)
- [🛠️ More Coming Soon...](#️-more-coming-soon)

---

## ✅ 1. Add Binary – [LeetCode 67](https://leetcode.com/problems/add-binary/)

**Problem:** Add two binary strings and return their sum (also as a binary string).

**Key Learnings:**
- Use `size() - 1` to get the last index.
- Add digits from the end, and keep track of carry.
- Build result from the **front** (prepend):
  ```cpp
  result = to_string(sum % 2) + result;
````

* Use a loop like:

  ```cpp
  for (int i = a.size() - 1, j = b.size() - 1; i >= 0 || j >= 0 || carry; i--, j--) {
      int sum = carry;
      if (i >= 0) sum += a[i] - '0';
      if (j >= 0) sum += b[j] - '0';
      result = to_string(sum % 2) + result;
      carry = sum / 2;
  }
  ```

---

## ✅ 2. 01 Matrix – [LeetCode 542](https://leetcode.com/problems/01-matrix/)

**Problem:** Given a matrix of 0s and 1s, return a matrix where each 1 contains the distance to its nearest 0.

**Key Learnings:**

* To initialize a 2D vector of size `n x m` with a default value:

  ```cpp
  vector<vector<int>> dist(n, vector<int>(m, 1e5)); // large value
  ```

* Use a **two-pass DP** approach:

  * **Top-Left to Bottom-Right**:

    ```cpp
    if (i > 0)    dist[i][j] = min(dist[i][j], dist[i - 1][j] + 1);
    if (j > 0)    dist[i][j] = min(dist[i][j], dist[i][j - 1] + 1);
    ```
  * **Bottom-Right to Top-Left**:

    ```cpp
    if (i < n - 1)  dist[i][j] = min(dist[i][j], dist[i + 1][j] + 1);
    if (j < m - 1)  dist[i][j] = min(dist[i][j], dist[i][j + 1] + 1);
    ```

* Initialize 0s with distance 0, and 1s with a large value like `1e5`.

---

## 🛠️ More Coming Soon...

I'm actively solving more problems and will update this repo regularly.
Stay tuned---

## 🙌 Contributions

This repo is for personal preparation, but if you're a fellow learner and want to collaborate or suggest problems, feel free to open an issue or PR!

---

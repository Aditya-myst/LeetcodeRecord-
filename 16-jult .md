

### 🔹 1. **Find Minimum in Rotated Sorted Array**

> **Core Hint:**
> Use **binary search** by comparing the middle element to the rightmost element to determine which half is unsorted (and thus contains the minimum).
> ➡ The minimum always lies in the **unsorted** half.

---

### 🔹 2. **Search in Rotated Sorted Array** (No duplicates)

> **Core Hint:**
> Apply **modified binary search** by determining whether the **left or right half is sorted**, and then decide whether the target lies in that half.
> ➡ Use the property of a **sorted half** to narrow your search.

---

### 🔹 3. **Search in Rotated Sorted Array II** (With duplicates)

> **Core Hint:**
> Same logic as question 2, but duplicates can **mask the sorted half**, especially when `nums[mid] == nums[left] == nums[right]`.
> ➡ To handle this, **skip duplicates** at the boundaries before applying the usual binary search logic.

---

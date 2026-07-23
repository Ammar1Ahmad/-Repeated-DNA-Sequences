
<div align="center">

# 🧬 LeetCode 187. Repeated DNA Sequences

<img src="https://img.shields.io/badge/LeetCode-187-orange?style=for-the-badge&logo=leetcode" />
<img src="https://img.shields.io/badge/Difficulty-Medium-yellow?style=for-the-badge" />
<img src="https://img.shields.io/badge/Language-Java-red?style=for-the-badge&logo=openjdk" />
<img src="https://img.shields.io/badge/Approach-HashSet%20%2B%20Sliding%20Window-blue?style=for-the-badge" />
<img src="https://img.shields.io/badge/Time-O(n)-brightgreen?style=for-the-badge" />
<img src="https://img.shields.io/badge/Space-O(n)-success?style=for-the-badge" />

### Efficient Hashing Solution for Detecting Repeated 10-Letter DNA Sequences

*A clean, interview-ready Java implementation with detailed explanation, algorithm, correctness proof, and complexity analysis.*

</div>

---

# 📖 Overview

DNA molecules are composed of four nucleotides:

| Symbol | Nucleotide |
|:------:|:-----------|
| 🅰️ | Adenine |
| 🌙 | Cytosine |
| 🟢 | Guanine |
| 🔺 | Thymine |

Given a DNA string, the objective is to identify every **10-character-long sequence** that appears **more than once**.

This repository demonstrates an optimal **Sliding Window + HashSet** solution that efficiently detects duplicate sequences while maintaining excellent readability.

---

# ✨ Features

✅ Clean Java Implementation

✅ Interview Friendly Solution

✅ Sliding Window Technique

✅ HashSet Based Duplicate Detection

✅ Detailed Explanation

✅ Complexity Analysis

✅ Well Documented Code

---

# 🚀 Approach

The algorithm slides a fixed window of **10 characters** across the DNA string.

For every window:

- Extract the current DNA sequence.
- Store unseen sequences inside a HashSet.
- If a sequence appears again, save it into the answer set.
- Finally return every repeated sequence.

Since every substring is processed only once, the solution remains highly efficient.

---

# 📊 Complexity

| Operation | Complexity |
|-----------|------------|
| Time | **O(n)** |
| Space | **O(n)** |

---

# 🛠️ Technologies

- Java
- HashSet
- Sliding Window
- String Processing

---

# 💡 Why This Solution?

- Linear Time Complexity
- Constant Window Size
- No Redundant Processing
- Easy to Understand
- Production Quality Code
- Ideal for Coding Interviews

---

# 📂 Repository Structure

```
187-Repeated-DNA-Sequences/
│
├── README.md
├── Solution.java
└── LICENSE
```

---

# ⭐ If you found this repository helpful

Give it a ⭐ on GitHub to support future high-quality LeetCode solutions!

---

> **LeetCode Medium**  
> Find every 10-letter-long DNA sequence that appears more than once in a DNA string.

---

## Problem Statement

A DNA sequence consists of four nucleotides:

- `A`
- `C`
- `G`
- `T`

Given a DNA string `s`, return all **10-letter-long substrings** that occur **more than once** in the DNA molecule.

The answer may be returned in **any order**.

---

## Example

### Example 1

```text
Input:
s = "AAAAACCCCCAAAAACCCCCCAAAAAGGGTTT"

Output:
["AAAAACCCCC","CCCCCAAAAA"]
```

### Example 2

```text
Input:
s = "AAAAAAAAAAAAA"

Output:
["AAAAAAAAAA"]
```

---

## Approach

Since every valid DNA sequence has a **fixed length of 10**, we simply slide a window of size **10** across the string.

For every window:

1. Extract the current 10-character substring.
2. If it has never been seen before, store it in a `seen` set.
3. If it has already been seen, insert it into the answer set.
4. Using a set for the result automatically removes duplicate outputs.

This allows each substring to be processed only once while efficiently detecting repeated sequences.

---

## Algorithm

1. Initialize two hash sets:
   - `seen` → stores every unique 10-character sequence.
   - `answer` → stores repeated sequences.
2. Traverse the string with a sliding window of length `10`.
3. Extract the current substring.
4. If it already exists in `seen`, add it to `answer`.
5. Otherwise, insert it into `seen`.
6. Return all elements from `answer`.

---

## Correctness

- Every possible 10-character substring is examined exactly once.
- The first occurrence of a sequence is stored in `seen`.
- Any later occurrence is recognized immediately and inserted into the result.
- Since the result is stored in a set, every repeated DNA sequence appears exactly once in the final answer.

Therefore, the algorithm correctly returns all repeated 10-letter DNA sequences.

---

## Complexity Analysis

- **Time Complexity:** `O(n)`
  - Each 10-character substring is processed once.
  - Since the substring length is constant (`10`), extraction is effectively constant time.

- **Space Complexity:** `O(n)`
  - Hash sets store previously encountered sequences.

---

## Java Solution

```java
class Solution {
    public List<String> findRepeatedDnaSequences(String s) {
        Set<String> ans = new HashSet<>();
        Set<String> seen = new HashSet<>();

        for (int i = 0; i + 10 <= s.length(); ++i) {
            String seq = s.substring(i, i + 10);

            if (seen.contains(seq))
                ans.add(seq);

            seen.add(seq);
        }

        return new ArrayList<>(ans);
    }
}
```

---

## Key Insights

- The sequence length is fixed (`10`), making a sliding window a natural choice.
- A hash set provides **O(1)** average lookup and insertion.
- Using a second set for repeated sequences prevents duplicate entries in the final answer.
- This solution is simple, readable, and optimal for the given constraints.

---

## Tags

- String
- HashSet
- Sliding Window
- Hashing

---

## Summary

This solution efficiently scans the DNA string using a fixed-size sliding window and leverages hash sets to detect repeated sequences in **linear time**, making it an optimal and clean approach for this problem.

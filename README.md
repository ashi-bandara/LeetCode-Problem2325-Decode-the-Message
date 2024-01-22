
# LeetCode Challenge D37
## Overview

Welcome to my LeetCode solution repository! This project addresses the coding challenge presented by [2325. Decode the Message](https://leetcode.com/problems/decode-the-message/). Below, you'll find details about the problem, my approach to solving it, and the implemented solution.

## Problem Statement
You are given the strings  `key`  and  `message`, which represent a cipher key and a secret message, respectively. The steps to decode  `message`  are as follows:

1.  Use the  **first**  appearance of all 26 lowercase English letters in  `key`  as the  **order**  of the substitution table.
2.  Align the substitution table with the regular English alphabet.
3.  Each letter in  `message`  is then  **substituted**  using the table.
4.  Spaces  `' '`  are transformed to themselves.

-   For example, given  `key = "happy boy"`  (actual key would have  **at least one**  instance of each letter in the alphabet), we have the partial substitution table of (`'h' -> 'a'`,  `'a' -> 'b'`,  `'p' -> 'c'`,  `'y' -> 'd'`,  `'b' -> 'e'`,  `'o' -> 'f'`).

**Example**

![](https://assets.leetcode.com/uploads/2022/05/08/ex1new4.jpg)

> **Input:** key = "the quick brown fox jumps over the lazy dog", message = "vkbs bs t suepuv"
> 
>**Output:** "this is a secret"
> 
>**Explanation:** The diagram above shows the substitution table.
It is obtained by taking the first appearance of each letter in "**the** **quick** **brown** **f**o**x** **j**u**mps** o**v**er the **lazy** **d**o**g**".

**Language Used**
> Java

**Difficulty**
> Easy

## Solution Overview
The `key` represents a mapping of certain characters to their corresponding positions in the English alphabet. The program uses two lists: `result` to store the decoded characters and `uniqueKey` to keep track of unique characters in the `key` excluding spaces.

In the first loop, the program iterates through each character in the `key`, adding non-space characters to the `uniqueKey` list. This ensures that duplicate characters are not considered in the decoding process. The second loop processes each character in the `message`. If the character is not a space, it looks up its index in the `uniqueKey` list and retrieves the corresponding character from the English alphabet, adding it to the `result` list. If the character is a space, it simply adds a space to the `result` list. Finally, the decoded message is constructed by converting the `result` list to a string.

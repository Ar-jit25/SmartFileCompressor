# Smart File Compression Utility using Huffman Coding

A lossless file compression and decompression utility implemented in C++ using the Huffman Coding algorithm.

This project compresses text files by assigning variable-length binary codes to characters based on their frequencies. Frequently occurring characters receive shorter codes, while less frequent characters receive longer codes, resulting in reduced file size without losing information.

---

## Features

- Lossless file compression
- File decompression
- Huffman Tree construction
- Priority Queue (Min Heap) implementation
- Compression statistics
- Command-line interface
- Supports ASCII text files

---

## Algorithms & Data Structures Used

### Huffman Coding

Huffman Coding is a greedy algorithm used for lossless data compression.

Steps:

1. Count frequency of each character.
2. Build a Min Heap based on frequencies.
3. Construct the Huffman Tree.
4. Generate Huffman Codes for each character.
5. Encode the file using these codes.
6. Decode by traversing the Huffman Tree.

---

## Data Structures

- Priority Queue (Min Heap)
- Binary Tree (Huffman Tree)
- Hash Map / Encoding Table
- File Streams

---

## Project Structure

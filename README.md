# Smart File Compressor

A C++ implementation of a **lossless file compression and decompression system** based on the **Huffman Coding Algorithm**. The project compresses text files by assigning shorter binary codes to frequently occurring characters and longer codes to less frequent characters, reducing storage requirements while preserving data integrity.

---

## Features

* Lossless file compression
* File decompression with exact data recovery
* Huffman Tree generation using character frequencies
* Binary file storage for compressed output
* Custom metadata serialization for tree reconstruction
* Efficient use of priority queues and binary trees

---

## Tech Stack

* Language: C++
* STL Containers:

  * Priority Queue
  * Vector
  * String
  * File Streams
* Algorithms:

  * Huffman Coding
  * Greedy Algorithm
  * Tree Traversal

---

## Project Structure

```text
SmartFileCompressor/
│
├── include/
│   ├── HuffmanNode.h
│   ├── HuffmanTree.h
│   ├── Compressor.h
│   └── Decompressor.h
│
├── src/
│   ├── HuffmanTree.cpp
│   ├── Compressor.cpp
│   ├── Decompressor.cpp
│   └── main.cpp
│
├── input/
│   └── sample.txt
│
├── output/
│   ├── compressed.huf
│   └── decompressed.txt
│
└── README.md
```

*(Modify the structure above if your actual folder names differ.)*

---

## How It Works

### 1. Frequency Analysis

The program scans the input file and counts the occurrence of each character.

Example:

```text
Input:
aaabbc

Frequency Table:
a → 3
b → 2
c → 1
```

---

### 2. Huffman Tree Construction

A min-priority queue is used to repeatedly merge the two least frequent nodes until a single Huffman Tree is formed.

```text
        (6)
       /   \
     (3)   (3)
     a    /   \
         b     c
```

---

### 3. Code Generation

Tree traversal generates binary codes for each character.

```text
a → 0
b → 10
c → 11
```

---

### 4. Compression

The original file content is replaced with Huffman codes and stored in a compressed binary format.

Example:

```text
Original:
aaabbc

Encoded:
000101011
```

---

### 5. Decompression

The Huffman Tree is reconstructed from stored metadata and the encoded bitstream is decoded back to the original text.

```text
Compressed File
        ↓
Rebuild Huffman Tree
        ↓
Decode Bits
        ↓
Original File Restored
```

---

## Data Structures Used

| Data Structure | Purpose                        |
| -------------- | ------------------------------ |
| Priority Queue | Build Huffman Tree efficiently |
| Binary Tree    | Represent Huffman Coding Tree  |
| Vector         | Store encoded data             |
| File Streams   | Read/write files               |
| Strings        | Code generation and decoding   |

---

## Time Complexity

### Building Frequency Table

```text
O(n)
```

### Building Huffman Tree

```text
O(k log k)
```

where:

* n = total characters
* k = unique characters

### Encoding

```text
O(n)
```

### Decoding

```text
O(n)
```

---

## Sample Workflow

```text
Input File
     ↓
Frequency Analysis
     ↓
Build Huffman Tree
     ↓
Generate Codes
     ↓
Compress File (.huf)
     ↓
Store Metadata
     ↓
Decompress
     ↓
Original File Restored
```

---

## Learning Outcomes

This project demonstrates practical implementation of:

* Huffman Coding
* Greedy Algorithms
* Priority Queues (Min Heaps)
* Binary Trees
* File Handling in C++
* Serialization and Deserialization
* Data Compression Techniques

---

## Future Improvements

* Support all 256 ASCII characters
* Compression ratio statistics
* Directory compression
* GUI interface
* Multi-file compression
* Command-line argument support
* Performance benchmarking

---

## Author

Arjit Tiwari

Built to explore real-world applications of Data Structures, Algorithms, and File Compression techniques in C++.

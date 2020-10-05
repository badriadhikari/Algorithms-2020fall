# Homework 5

## Read sections 16.3 from CLRS
Please read this with the goal of using the knowledge to do the homework below.

## Watch the recorded lectures
1. [Huffman coding and Huffman trees](https://youtu.be/JsTptu56GM8)
1. [Tracing the Huffman's algorithm - How does the Huffman's algorithm work?](https://youtu.be/qE4tfsiTGjE)

## Question 1
When we use prefix codes to encode text, we can simply concatenate the codewords, i.e. we don't need a symbol to separate the codewords. Why doesn't this cause problems when decoding?

## Question 2
The table below represents two methods of encoding (fixed-length and variable-length). Discuss how the variable length encoding saves approximately 25% space.

Character |  a |  b |  c |  d |  e |  f 
-- | -- | -- | -- | -- | -- | -- 
Frequency | 45 | 13 | 12 | 16 | 9 | 5
Fixed-length codeword | 000 | 001 | 010 | 011 | 100 | 101
Variable-length codeword |  0 |  101 | 100 | 111 | 1101 | 1100

## Question 3
Create a string by concatenating your first name, middle name, and last name. Use the Huffman coding algorithm to create a codeword for each of the letter in your name. Start by creating a frequency table of letters such that the characters are ordered by their frequency. Most importantly, show the steps of the Huffman's algorithm by displaying how the Huffman (binary) tree grows after each step. How many bits are required for encoding your name? How many bits would it require if we were to use fixed-length codewords?

## Question 4 
What is the optimal Huffman code for the following set of frequencies, based on the first n Fibonacci numbers? Show the steps of the Huffman's algorithm by displaying how the Huffman (binary) tree grows after each step. Optionally, you can also use the Python code below to verify your answer. (from CLRS 16.3-3)
```
a:1  b:1  c:2  d:3  e:5  f:8  g:13  h:21
```

## Question 5 (programming)
The file [reddit_relationshipadvice_legaladvice_2000](./reddit_relationshipadvice_legaladvice_2000.txt) contains the texts of legal relationship advice obtained from Reddit. Compres the file using the Huffman's algorithm implemented below. Extend the code to read the file and write the compressed file. How will you verify that the codewords make sense (i.e. roughly correct)?

----
# Python implementation of the Huffman's algorithm 
```python
import heapq

def huffman_encode(frequency):
    heap = [[weight, [symbol, '']] for symbol, weight in frequency.items()]
    heapq.heapify(heap)
    while len(heap) > 1:
        lo = heapq.heappop(heap)
        hi = heapq.heappop(heap)
        for pair in lo[1:]:
            pair[1] = '0' + pair[1]
        for pair in hi[1:]:
            pair[1] = '1' + pair[1]
        heapq.heappush(heap, [lo[0] + hi[0]] + lo[1:] + hi[1:])
    return sorted(heapq.heappop(heap)[1:], key=lambda p: (len(p[-1]), p))

data = 'aaccbaaaaaaaaddaaabdebacbaafabaadaaadacabdaefcaaeeaabfdcaaecbbbadafeaaaadadfbdcdabdeccdcadaadbaeaaec'
print('Data:')
print(data)

from collections import defaultdict
frequency = defaultdict(int)

for symbol in data:
    frequency[symbol] += 1

print('')
print('Symbol frequencies:')
print(frequency)

huff = huffman_encode(frequency)

print('')
print('Huffman codes:')
for p in huff:
    print (p[0], str(frequency[p[0]]), p[1])
```
```
Data:
aaccbaaaaaaaaddaaabdebacbaafabaadaaadacabdaefcaaeeaabfdcaaecbbbadafeaaaadadfbdcdabdeccdcadaadbaeaaec

Symbol frequencies:
defaultdict(<class 'int'>, {'a': 45, 'c': 12, 'b': 13, 'd': 16, 'e': 9, 'f': 5})

Huffman codes:
a 45 0
b 13 101
c 12 100
d 16 111
e 9 1101
f 5 1100
```

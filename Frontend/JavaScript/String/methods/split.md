# Split Method

In JavaScript, the split method is used to split a string into an array of substrings. 

Think of it like breaking a bar of chocolate into individual pieces. Each piece is a part of the original bar, but now you have them separately.

Here's how it works:

# 1. Syntax: 
string.split(separator, limit)

# 2. Parameters:

## separator (optional): 
The character or pattern where the split should occur.

If omitted, the entire string becomes a single element in the resulting array.

## limit (optional): 
A number defining the maximum number of splits. 
The array will contain at most this many elements.

# 3. Returns: 
An array of substrings.

# 4. Original string remains unchanged: 
Just like slicing an array, splitting a string does not alter the original string.


Example:
```
let sentence = 'The quick brown fox jumps over the lazy dog';

// Split the sentence by spaces
let words = sentence.split(' '); 

// Returns: ['The', 'quick', 'brown', 'fox', 'jumps', 'over', 'the', 'lazy', 'dog']

```

In this example, words will be an array where each element is a word from the sentence, split at every space. The original sentence string remains as it is.
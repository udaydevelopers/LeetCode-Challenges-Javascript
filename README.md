# Javascript Coding Challenge

## 1. Question

You are given an array of strings. Write a function that takes the array as input and returns a new array containing only the strings that have the letter 'a' in them. Ignore case sensitivity.

For example, given the input ['Apple', 'Banana', 'Cherry', 'Date'], the function should return ['Apple', 'Banana'].

## Constraints

- The function should ignore case sensitivity (e.g., 'a' and 'A' should be considered the same).
- The original array should not be modified.

## Test Cases

Input: ['Apple', 'Banana', 'Cherry', 'Date']
Output: ['Apple', 'Banana']

Input: ['Antelope', 'Bear', 'Cat', 'Dog']
Output: ['Antelope', 'Cat']

Input: ['Elephant', 'Frog', 'Giraffe', 'Horse']
Output: []

## Solution Code
```javascript
function filterStrings(arr) {
  return arr.filter(str => str.toLowerCase().includes('a'));
}

// Test cases
console.log(filterStrings(['Apple', 'Banana', 'Cherry', 'Date'])); // Expected output: ['Apple', 'Banana']
console.log(filterStrings(['Antelope', 'Bear', 'Cat', 'Dog'])); // Expected output: ['Antelope', 'Cat']
console.log(filterStrings(['Elephant', 'Frog', 'Giraffe', 'Horse'])); // Expected output: []
```

## 2. Question

You are given an array of integers. Write a function that takes the array as input and returns the sum of all the even numbers in the array.

For example, given the input [1, 2, 3, 4, 5, 6], the function should return 12 (which is the sum of 2, 4, and 6).

## Constraints

- The function should only consider even numbers for the sum.
- The original array should not be modified.

## Test Cases

Input: [1, 2, 3, 4, 5, 6]
Output: 12

Input: [10, 11, 12, 13, 14, 15]
Output: 36

Input: [2, 4, 6, 8, 10]
Output: 30

## Solution
```javascript
function sumOfEvenNumbers(arr) {
  return arr.reduce((sum, num) => num % 2 === 0 ? sum + num : sum, 0);
}

// Test cases
console.log(sumOfEvenNumbers([1, 2, 3, 4, 5, 6])); // Expected output: 12
console.log(sumOfEvenNumbers([10, 11, 12, 13, 14, 15])); // Expected output: 36
console.log(sumOfEvenNumbers([2, 4, 6, 8, 10])); // Expected output: 30
```

## 3. Question

You are given an array of numbers representing stock prices on different days. Write a function that takes the array as input and returns the maximum profit that can be achieved by buying and selling the stock at most once. If no profit can be made, return 0.

For example, given the input [7, 1, 5, 3, 6, 4], the function should return 5, which is the maximum profit that can be achieved by buying on day 2 (price = 1) and selling on day 5 (price = 6).

## Constraints

- The function should return 0 if no profit can be made.
- The original array should not be modified.

## Test Cases

Input: [7, 1, 5, 3, 6, 4]
Output: 5

Input: [7, 6, 4, 3, 1]
Output: 0

Input: [3, 6, 8, 4, 9, 1]
Output: 6

## Solution

```javascript
function maxProfit(prices) {
  let minPrice = Infinity;
  let maxProfit = 0;
  
  for (let price of prices) {
    if (price < minPrice) {
      minPrice = price;
    } else if (price - minPrice > maxProfit) {
      maxProfit = price - minPrice;
    }
  }
  
  return maxProfit;
}

// Test cases
console.log(maxProfit([7, 1, 5, 3, 6, 4])); // Expected output: 5
console.log(maxProfit([7, 6, 4, 3, 1])); // Expected output: 0
console.log(maxProfit([3, 6, 8, 4, 9, 1])); // Expected output: 6

```

## 4. Question

You are given a string containing parentheses, brackets, and curly braces. Write a function that determines if the input string is valid. A valid string is one where every opening parenthesis, bracket, or curly brace has a corresponding closing parenthesis, bracket, or curly brace of the same type, and the pairs are properly nested.

For example, the input "{[()()]}" is valid, but "{[(])}" is not.

## Constraints

- The function should return true if the input string is valid and false otherwise.
- The original string should not be modified.

## Test Cases

Input: "{[()()]}"
Output: true

Input: "{[(])}"
Output: false

Input: "{{[[(())]]}}"
Output: true

## Starter Code

```javascript
function isValid(s) {
  const stack = [];
  const pairs = {
    '(': ')',
    '[': ']',
    '{': '}'
  };

  for (let i = 0; i < s.length; i++) {
    const char = s[i];
    if (char === '(' || char === '[' || char === '{') {
      stack.push(char);
    } else {
      const top = stack.pop();
      if (pairs[top] !== char) {
        return false;
      }
    }
  }

  return stack.length === 0;
}

// Test cases
console.log(isValid("{[()()]}")); // Expected output: true
console.log(isValid("{[(])}")); // Expected output: false
console.log(isValid("{{[[(())]]}}")); // Expected output: true
````

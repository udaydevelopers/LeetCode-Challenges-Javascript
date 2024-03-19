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

function filterStrings(arr) {
  return arr.filter(str => str.toLowerCase().includes('a'));
}

// Test cases
console.log(filterStrings(['Apple', 'Banana', 'Cherry', 'Date'])); // Expected output: ['Apple', 'Banana']
console.log(filterStrings(['Antelope', 'Bear', 'Cat', 'Dog'])); // Expected output: ['Antelope', 'Cat']
console.log(filterStrings(['Elephant', 'Frog', 'Giraffe', 'Horse'])); // Expected output: []



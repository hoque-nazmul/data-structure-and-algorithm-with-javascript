# data-structure-and-algorithm-with-javascript

## Table of Contents

1. [Time Comlexity](#time-complexity)
2. [Space complexity](#space-complexity)
3. [Searching Algorithm](#searching-algorithm)
    - [Linear Search](#linear-search)
    - [Binary Search](#binary-search)
4. [Sorting Algorithm](#sorting-algorithm)
    - [Selection Sort](#selection-sort)
    - [Bubble Sort](#bubble-sort)

## Time Complexity
```javascript
// time complexity O(1)
const n = 10;
const m = 20;
const x = m + n;
console.log(x);

// time complexity 0(1)
const total = n * (n + 1) / 2;
console.log(total);

// time complexity O(n2)
const input = 10;
let total = 0;
for (let i = 1; i <= input; i++) {
    total += i;
}
console.log(total);

// time complexity O(n3)
const input = 10;
for (let i = 0; i < input; i++) {
    for (let j = 0; j < input; j++) {
        console.log(j);
    }
}
```

## Space Complexity
```javascript
const nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
const evenNums = [];
for (let i = 0; i < nums.length; i++) {
    if (nums[i] % 2 === 0) {
        evenNums.push(nums[i]);
    }
}
console.log(evenNums); // output: [2, 4, 6, 8, 10]
```
**[⬆ back to top](#table-of-contents)**

# Searching Algorithm
## Linear Search

```javascript
// Implementing Linear Search
const nums = [12, 5, 22, 14, 10, 89, 65, 34]
const n = 65;
const linearSearch = (inputArr, element) => {
    for (let i = 0; i < inputArr.length; i++) {
        if (inputArr[i] === element) {
            return i;
        }
    }
    return -1;
}
linearSearch(nums, n); // output: 6

// Implementing Linear Search by JS Built-in Method
nums.indexOf(n); // output: 6
// or
nums.includes(n); // It returns true/false - output: true
```

## Binary Search
```javascript
// Implementing Binary Search
const nums = [23, 34, 54, 65, 76, 87, 95, 99, 120, 150]
const binarySearch = (inputArr, element) => {
    let leftNodeIndex = 0;
    let rightNodeIndex = inputArr.length - 1;

    while (leftNodeIndex <= rightNodeIndex) {
        let midNode = Math.floor((leftNodeIndex + rightNodeIndex) / 2);

        if (inputArr[midNode] === element) {
            return midNode;
        }
        if (inputArr[midNode] < element) {
            leftNodeIndex = midNode + 1;
        } else {
            rightNodeIndex = midNode - 1;
        }
    }
    return -1;
}
console.log(binarySearch(nums, 65));  // output: 3
```
**[⬆ back to top](#table-of-contents)**

# Sorting Algorithm 
## Selection Sort
```javascript
// Implementing Selection Sort
const nums = [87, 43, 32, 33, 2, 20, 22];

const selectionSort = (arr) => {
    const len = arr.length;
    for (let i = 0; i < len; i++) {
        let min = i;
        for (let j = min + 1; j < len; j++) {
            if (arr[min] > arr[j]) {
                min = j;
            }
        }

        if (min !== i) {
            [arr[i], arr[min]] = [arr[min], arr[i]];
        }
    }
    return arr;
}
console.log(selectionSort(nums)) // output: [2, 20, 22, 32, 33, 43, 87]
```
## Bubble Sort
```javascript
// Implementing Selection Sort
const nums = [87, 43, 32, 33, 2, 20, 22];

const bubbleSort = (inputArr) => {
    let len = inputArr.length;
    for (let i = 0; i < len; i++) {

        for (let j = 0; j < len; j++) {
            if (inputArr[j] > inputArr[j + 1]) {
                [ inputArr[j], inputArr[j + 1] ] = [ inputArr[j + 1], inputArr[j] ]
            }
        }

    }
    return inputArr;
};
console.log(bubbleSort(nums)); // output: [2, 20, 22, 32, 33, 43, 87]
```
**[⬆ back to top](#table-of-contents)**
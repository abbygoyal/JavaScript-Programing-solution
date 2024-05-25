# JavaScript-Programing-solutions



Sure, I'll provide detailed solutions for each of the tasks you listed:



1. **Program to find the longest word in a given sentence:**
```javascript
function findLongestWord(sentence) {
    let words = sentence.split(' ');
    let longestWord = '';

    for (let word of words) {
        if (word.length > longestWord.length) {
            longestWord = word;
        }
    }

    return longestWord;
}

console.log(findLongestWord("I love programming in JavaScript"));
```

2. **How to check whether a string is a palindrome or not:**
```javascript
function isPalindrome(str) {
    let reversedStr = str.split('').reverse().join('');
    return str === reversedStr;
}

console.log(isPalindrome("madam"));  // true
console.log(isPalindrome("hello"));  // false
```

3. **Program to remove duplicates from an array:**
```javascript
function removeDuplicates(arr) {
    return [...new Set(arr)];
}

console.log(removeDuplicates([1, 2, 2, 3, 4, 4, 5]));  // [1, 2, 3, 4, 5]
```

4. **Program to find the reverse of a string without using built-in methods:**
```javascript
function reverseString(str) {
    let reversedStr = '';
    for (let i = str.length - 1; i >= 0; i--) {
        reversedStr += str[i];
    }
    return reversedStr;
}

console.log(reverseString("hello"));  // "olleh"
```

5. **Find the max count of consecutive 1’s in an array:**
```javascript
function maxConsecutiveOnes(arr) {
    let maxCount = 0;
    let currentCount = 0;

    for (let num of arr) {
        if (num === 1) {
            currentCount++;
            if (currentCount > maxCount) {
                maxCount = currentCount;
            }
        } else {
            currentCount = 0;
        }
    }

    return maxCount;
}

console.log(maxConsecutiveOnes([1, 1, 0, 1, 1, 1]));  // 3
```

6. **Find the factorial of a given number:**
```javascript
function factorial(n) {
    if (n === 0) {
        return 1;
    }
    return n * factorial(n - 1);
}

console.log(factorial(5));  // 120
```

7. **Merge and sort two sorted arrays:**
```javascript
function mergeSortedArrays(arr1, arr2) {
    let mergedArray = arr1.concat(arr2);
    return mergedArray.sort((a, b) => a - b);
}

console.log(mergeSortedArrays([0, 3, 4, 31], [4, 6, 30]));  // [0, 3, 4, 4, 6, 30, 31]
```

8. **Check if every value in arr1 has its corresponding value squared in arr2:**
```javascript
function hasCorrespondingSquares(arr1, arr2) {
    let map1 = {};
    let map2 = {};

    for (let num of arr1) {
        map1[num] = (map1[num] || 0) + 1;
    }

    for (let num of arr2) {
        map2[num] = (map2[num] || 0) + 1;
    }

    for (let key in map1) {
        if (!map2[key * key] || map2[key * key] !== map1[key]) {
            return false;
        }
    }

    return true;
}

console.log(hasCorrespondingSquares([1, 2, 3], [1, 4, 9]));  // true
console.log(hasCorrespondingSquares([1, 2, 3], [1, 4, 8]));  // false
```

9. **Check if one string can be formed by rearranging the letters of another string:**
```javascript
function areAnagrams(str1, str2) {
    if (str1.length !== str2.length) {
        return false;
    }
    let sortedStr1 = str1.split('').sort().join('');
    let sortedStr2 = str2.split('').sort().join('');
    return sortedStr1 === sortedStr2;
}

console.log(areAnagrams("listen", "silent"));  // true
console.log(areAnagrams("hello", "world"));    // false
```

10. **Get unique objects from an array:**
```javascript
function getUniqueObjects(arr) {
    let uniqueNames = new Set();
    let uniqueObjects = [];

    for (let obj of arr) {
        if (!uniqueNames.has(obj.name)) {
            uniqueNames.add(obj.name);
            uniqueObjects.push(obj);
        }
    }

    return uniqueObjects;
}

console.log(getUniqueObjects([{name: "sai"}, {name:"Nang"}, {name: "sai"}, {name:"Nang"}, {name: "111111"}]));
// [{name: "sai"}, {name:"Nang"}, {name: "111111"}]
```

11. **Find the maximum number in an array:**
```javascript
function findMaxNumber(arr) {
    return Math.max(...arr);
}

console.log(findMaxNumber([1, 2, 3, 4, 5]));  // 5
```

12. **Function that returns a new array with only the even numbers:**
```javascript
function filterEvenNumbers(arr) {
    return arr.filter(num => num % 2 === 0);
}

console.log(filterEvenNumbers([1, 2, 3, 4, 5, 6]));  // [2, 4, 6]
```

13. **Function to check if a given number is prime:**
```javascript
function isPrime(num) {
    if (num <= 1) {
        return false;
    }
    for (let i = 2; i <= Math.sqrt(num); i++) {
        if (num % i === 0) {
            return false;
        }
    }
    return true;
}

console.log(isPrime(7));  // true
console.log(isPrime(4));  // false
```

14. **Find the largest element in a nested array:**
```javascript
function findLargestInNestedArray(arr) {
    let flattenArray = arr.flat(Infinity);
    return Math.max(...flattenArray);
}

console.log(findLargestInNestedArray([[3, 4, 58], [709, 8, 9, [10, 11]], [111, 2]]));  // 709
```

15. **Function that returns the Fibonacci sequence up to a given number of terms:**
```javascript
function fibonacciSequence(n) {
    if (n <= 0) {
        return [];
    }
    if (n === 1) {
        return [0];
    }
    let seq = [0, 1];
    for (let i = 2; i < n; i++) {
        seq.push(seq[i - 1] + seq[i - 2]);
    }
    return seq;
}

console.log(fibonacciSequence(5));  // [0, 1, 1, 2, 3]
```

16. **Function to count the occurrences of each character in a string:**
```javascript
function countCharacterOccurrences(str) {
    let charCount = {};
    for (let char of str) {
        charCount[char] = (charCount[char] || 0) + 1;
    }
    return charCount;
}

console.log(countCharacterOccurrences("hello"));  // {h: 1, e: 1, l: 2, o: 1}
```

17. **Function that sorts an array of numbers in ascending order:**
```javascript
function sortArrayAscending(arr) {
    return arr.sort((a, b) => a - b);
}

console.log(sortArrayAscending([3, 1, 4, 1, 5, 9]));  // [1, 1, 3, 4, 5, 9]
```

18. **Function that sorts an array of numbers in descending order:**
```javascript
function sortArrayDescending(arr) {
    return arr.sort((a, b) => b - a);
}

console.log(sortArrayDescending([3, 1, 4, 1, 5, 9]));  // [9, 5, 4, 3, 1, 1]
```

19. **Function that reverses the order of words in a sentence without using the built-in reverse() method:**
```javascript
function reverseWords(sentence) {
    let words = sentence.split(' ');
    let reversedSentence = '';
    for (let i = words.length - 1; i >= 0; i--) {
        reversedSentence += words[i] + (i > 0 ? ' ' : '');
    }
    return reversedSentence;
}

console.log(reverseWords("I love programming"));  // "programming love I"
```

20. **Function that flattens a nested array into a single-dimensional array:**
```javascript
function flattenArray(arr) {
    let flatArray = [];
    function flatten(arr) {
        for (let item of arr) {
            if (Array.isArray(item)) {
                flatten(item);
            } else {
                flatArray.push(item);
            }
        }
    }
    flatten(arr);


    return flatArray;
}

console.log(flattenArray([1, [2, [3, 4], 5], 6]));  // [1, 2, 3, 4, 5, 6]
```

21. **Function which converts string input into an object:**
```javascript
function stringToObj(path, value) {
    let keys = path.split('.');
    let obj = {};
    let temp = obj;
    for (let i = 0; i < keys.length - 1; i++) {
        temp[keys[i]] = {};
        temp = temp[keys[i]];
    }
    temp[keys[keys.length - 1]] = value;
    return obj;
}

console.log(stringToObj("a.b.c", "someValue"));  // {a: {b: {c: "someValue"}}}
```

These solutions cover the tasks you provided with a detailed explanation of each step.

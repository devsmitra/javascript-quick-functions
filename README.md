# Quick functions

Javascript quick functions codes you will always need (https://github.com/devsmitra/quick-functions)

# Array

### Shuffling an array is super easy with sort and random methods.

    const shuffleArray = (arr) => arr.sort(() => 0.5 - Math.random());
    console.log(shuffleArray([1, 2, 3, 4])); // [3, 2, 1, 4]

### Convert an object into a list of `[key, value]` pairs

    const toPairs = (obj) => Object.entries(obj);
    console.log(toPairs({ a: 1, b: 2, c: 3 })); // [['a', 1], ['b', 2], ['c', 3]]

### Convert a list of `[key, value]` pairs into an object

    const fromPairs = (pairs) => pairs.reduce((a, b) => ({ ...a, [b[0]]: b[1] }), {});
    console.log(fromPairs([['a', 1], ['b', 2], ['c', 3]])); // { a: 1, b: 2, c: 3 }

### Remove Duplicated from Array

    const removeDuplicated = (arr) => [...new Set(arr)];
    console.log(removeDuplicated([1, 2, 3, 3, 4, 4, 5, 5, 6])); // Result: [ 1, 2, 3, 4, 5, 6 ]

# Numbers

### Number is even or not

    const isEven = (num) => (num % 2 === 0);
    console.log(isEven(4)); // true

### Number is odd or not

    const isOdd = (num) => (num % 2 !== 0);
    console.log(isOdd(4)); // false

### Find the factorial of a number

    const factorial = (num) => (num === 0) ? 1 : num * factorial(num - 1);
    console.log(factorial(5)); // 120

### Find the sum of an array

    const sum = (arr) => arr.reduce((a, b) => a + b, 0);
    console.log(sum([1, 2, 3, 4])); // 10

### Find median of an array

    const median = (arr) => {
        const mid = Math.floor(arr.length / 2),
            nums = [...arr].sort((a, b) => a - b);
        return arr.length % 2 !== 0 ? nums[mid] : (nums[mid - 1] + nums[mid]) / 2;
    };
    console.log(median([1, 2, 3, 4])); // 2.5

### Find largest numbers

        const findLargest = (arr) => arr.map(subArr => Math.max(...subArr));
        console.log(findLargest([[4, 5, 1, 3], [13, 27, 18, 26], [32, 35, 37, 39], [1000, 1001, 857, 1]])); // [5, 27, 39, 1001]

### Find average of Numbers

    const findAverage = (arr) => arr.reduce((a, b) => a + b, 0) / arr.length;
    console.log(findAverage([1, 2, 3, 4])); // 2.5

### Find smallest numbers

        const findSmallest = (arr) => arr.map(subArr => Math.min(...subArr));
        console.log(findSmallest([[4, 5, 1, 3], [13, 27, 18, 26], [32, 35, 37, 39], [1000, 1001, 857, 1]])); // [1, 18, 32, 857]

### Find mode of an array

    const mode = (arr) => {
        const counts = arr.reduce((a, b) => {
            a[b] = (a[b] || 0) + 1;
            return a;
        }, {});
        const maxCount = Math.max(...Object.values(counts));
        return Object.keys(counts).filter(key => counts[key] === maxCount);
    };
    console.log(mode([3, 'a', 'a', 'a', 2, 3, 'a', 3, 'a', 2, 4, 9, 3])); // ['a']

### Find the range of an array

    const range = (arr) => Math.max(...arr) - Math.min(...arr);
    console.log(range([1, 2, 3, 4])); // 3

# String

### Reverse String

    const reverseString = (str) => str.split('').reverse().join('');
    console.log(reverseString('hello')); // olleh

### Find Longest Word in a String

    const findLongestWord = (str) => str.split(' ').reduce((a, b) => a.length > b.length ? a : b);
    console.log(findLongestWord('The quick brown fox jumped over the lazy dog')); // jumped

### Generate Title Case

    const titleCase = (str) => str.split(' ').map(word => word[0].toUpperCase() + word.slice(1).toLowerCase()).join(' ');
    console.log(titleCase('the quick brown fox')); // The Quick Brown Fox

### Is String Palindrome

    const isPalindrome = (str) => str === str.split('').reverse().join('');
    console.log(isPalindrome('madam')); // true

### Copy to Clipboard

    const copyToClipboard = (text) => navigator.clipboard.writeText(text);
    copyToClipboard("Hello World");

### Find a vowel in a string

    const findVowel = (str) => str.match(/[aeiou]/gi);
    console.log(findVowel('hello')); // ['e', 'o']

# Date

### Get the current date

    const getDate = () => new Date();
    console.log(getDate()); // 2020-05-25T09:57:37.869Z

### Find the day of the week

    const getDayName = (date) => {
        const days = ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday'];
        return days[date.getDay()];
    };
    console.log(getDayName(new Date())); // Friday

### Find the day of the year

    const getDayOfYear = (date) => {
        const firstDay = new Date(date.getFullYear(), 0, 1);
        return Math.ceil((date - firstDay) / 86400000);
    };
    console.log(getDayOfYear(new Date())); // 182

### Find the number of days in a month

    const getDaysInMonth = (date) => new Date(date.getFullYear(), date.getMonth() + 1, 0).getDate();
    console.log(getDaysInMonth(new Date())); // 31

### Find the current month

    const getMonthName = (date) => {
        const months = ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December'];
        return months[date.getMonth()];
    };
    console.log(getMonthName(new Date())); // March

### Find the number of seconds until midnight

    const getSecondsUntilMidnight = (date) => (24 - date.getHours()) * 60 * 60 + (60 - date.getMinutes()) * 60 + (60 - date.getSeconds());
    console.log(getSecondsUntilMidnight(new Date())); // 86400

### Log Time from Date

    const logTime = date => date.toTimeString().slice(0, 8);
    logTime(new Date()); // 09:57:37


    const logTime = date => date.toLocaleTimeString('en-GB');
    logTime(new Date()); // 09:57:37

# Styling

### Generate a random color

    const getRandomColor = () => `#${Math.floor(Math.random() * 16777215).toString(16)}`;
    console.log(getRandomColor()); // #f0f0f0

    const randomHex = () => `#${Math.floor(Math.random() * 0xffffff).toString(16).padEnd(6, "0")}`;
    console.log(randomHex()); // #f0f0f0

# Window

### Get selected text

    const getSelectedText = () => window.getSelection().toString();
    console.log(getSelectedText()); // Hello World

# DSA-BigO

In these drills, you'll practice determining the big O complexity of algorithms. For each drill, we'll provide a code snippet with a function, and you'll work out the big O complexity by analyzing the code without running it.

## 1. What is the Big O for this?
1) Determine the Big O for the following algorithm: You are sitting in a room with 15 people. You want to find a playmate for your dog, preferably of the same breed. So you want to know if anyone out of the 15 people have the same breed as your dog. You stand up and yell out, who here has a golden retriever and would like to be a playdate for my golden. Someone yells - "I do, be happy to bring him over"

*Solution* : O(1), because this function will only run once no matter how large the input.

2) Determine the Big O for the following algorithm: You are sitting in a room with 15 people. You want to find a playmate for your dog who is of the same breed. So you want to know if anyone out of the 15 people have the same breed as your dog. You start with the first person and ask him if he has a golden retriever. He says no, then you ask the next person, and the next, and the next until you find someone who has a golden or there is no one else to ask.

*Solution* : O(n), because the input will directly coorelate to the running times of the program.

## 2. Even or odd
What is the Big O of the following algorithm? Explain your answer
```
function isEven(value) {
    if (value % 2 === 0) {
        return true;
    }
    else {
        return false;
    }
}
```
*Solution* : O(1), because the function will only run once to check the condition compared to the input, no matter the size of the input.
## 3. Are you here?
What is the Big O of the following algorithm? Explain your answer
```
function areYouHere(arr1, arr2) {
    for (let i = 0; i < arr1.length; i++) {
        const el1 = arr1[i];
        for (let j = 0; j < arr2.length; j++) {
            const el2 = arr2[j];
            if (el1 === el2) return true;
        }
    }
    return false;
}
```
*Solution* : O(n^2), because the two nested loops will increase the time complexity polynomially(by a constant power) as you increase the inputs.
## 4. Doubler
What is the Big O of the following algorithm? Explain your answer
```
function doubleArrayValues(array) {
    for (let i = 0; i < array.length; i++) {
        array[i] *= 2;
    }
    return array;
}
```
*Solution* : O(n), because the for loop will have a linear or the same run time as the input is increased.
## 5. Naive search
What is the Big O of the following algorithm? Explain your answer
```
function naiveSearch(array, item) {
    for (let i = 0; i < array.length; i++) {
        if (array[i] === item) {
            return i;
        }
    }
}
```
*Solution* : O(n), because again the for loop will have a linear or the same runtime as the input is increased.
## 6. Creating pairs:
What is the Big O of the following algorithm? Explain your answer
```
function createPairs(arr) {
    for (let i = 0; i < arr.length; i++) {
        for(let j = i + 1; j < arr.length; j++) {
            console.log(arr[i] + ", " +  arr[j] );
        }
    }
}
```
*Solution* : O(n^2), because the two nested for loops will increase time complexity polonomially(by a constant power) as the size of the input increases.
## 7. Compute the sequence
What does the following algorithm do? What is its runtime complexity? Explain your answer
```
function compute(num) {
    let result = [];
    for (let i = 1; i <= num; i++) {

        if (i === 1) {
            result.push(0);
        }
        else if (i === 2) {
            result.push(1);
        }
        else {
            result.push(result[i - 2] + result[i - 3]);
        }
    }
    return result;
}
```
*Solution* : The algorithm is computing the fibonacci numbers (the sum of the previous two numbers in the array), this is O(n), becuase the for loop will have the same or linear runtime as the input increases.
## 8. An efficient search
In this example, we return to the problem of searching using a more sophisticated approach than in naive search, above. Assume that the input array is always sorted. What is the Big O of the following algorithm? Explain your answer
```
function efficientSearch(array, item) {
    let minIndex = 0;
    let maxIndex = array.length - 1;
    let currentIndex;
    let currentElement;

    while (minIndex <= maxIndex) {
        currentIndex = Math.floor((minIndex + maxIndex) / 2);
        currentElement = array[currentIndex];

        if (currentElement < item) {
            minIndex = currentIndex + 1;
        }
        else if (currentElement > item) {
            maxIndex = currentIndex - 1;
        }
        else {
            return currentIndex;
        }
    }
    return -1;
}
```
*Solution* : O(log(n)), because the sorted array (input) is halved each time the program is ran.
## 9. Random element
What is the Big O of the following algorithm? Explain your answer
```
function findRandomElement(arr) {
    return arr[Math.floor(Math.random() * arr.length)];
}
```
*Solution* : O(1), because this algorithm will only be ran once regardless of the size of the input.
## 10. What Am I?
What does the following algorithm do? What is the Big O of the following algorithm? Explain your answer
```
function isWhat(n) {
    if (n < 2 || n % 1 !== 0) {
        return false;
    }
    for (let i = 2; i < n; ++i) {
        if (n % i === 0) return false;
    }
    return true;
}
```
*Solution* : This program determines if the number (n) is a prime number or not, it is O(n) because it will only iterate through one time so the progression is linear compared to the size of the input.
## 11. Tower of Hanoi
The Tower of Hanoi is a very famous mathematical puzzle (some call it game!). This is how it goes:

There are three rods and a number of disks of different sizes which can slide onto any rod. The puzzle starts with the disks neatly stacked in ascending order of size on one rod, the smallest disk at the top (making a conical shape). The other two rods are empty to begin with.
The goal of the puzzle is to move the entire stack of rods to another rod (can't be the original rod where it was stacked before) where it will be stacked in the ascending order as well. This should be done obeying the following rules: 
* i) Only one disk may be moved at a time 
* ii) Each move consists of taking the upper disk from one of the rods and sliding it onto another rod, on top of the other disks that may already be present on that rod. 
* iii) A larger disk may not placed on top of a smaller disk  
  
Input:
```
Rod A	Rod B	Rod C
----		
---------		
-------------
```		
Output:
```
Rod A	Rod B	Rod C
----
---------
-------------
```
Derive an algorithm to solve the Tower of Hanoi puzzle.
Implement your algorithm using recursion. Your program should display each movement of the disk from one rod to another.
If you are given 5 disks, how do the rods look like after 7 recursive calls?
How many moves are needed to complete the puzzle with 3 disks? with 4 disks? with 5 disks?
What is the runtime of your algorithm?

*Solution* :  
 - Algorithm:
```
const towerOfHanoi = (disks, sourceRod, destinationRod, bufferRod) => {
    
    // Verify that disks exist
    if(disks >= 1) {
        // Move one of the disks to a 'bufferRod' using the destinationRod
        towerOfHanoi(disks - 1, sourceRod, bufferRod, destinationRod);

        // Move the remaining disk to the 'destinationRod'
        console.log('Move disk from rod', sourceRod, 'to rod', destinationRod);

        // Move the disk from 'bufferRod' to the 'destinationRod' by using the 'sourceRod'
        towerOfHanoi(disks - 1, bufferRod, destinationRod, sourceRod);
    }
    
    return;
}

// Example Call
towerOfHanoi(3, 'A', 'C', 'B');
```

- If you are given 5 disks, how do the rods look like after 7 recursive calls?  
```
Move disk from rod A to rod B
Move disk from rod A to rod C
Move disk from rod B to rod C
Move disk from rod A to rod B
Move disk from rod C to rod A
Move disk from rod C to rod B
Move disk from rod A to rod B

Rod A	            Rod B	            Rod C
---------------     ---- 
-----------------   ---------
                    -------------
     	
```
* How many moves are needed to complete the puzzle with 3 disks? with 4 disks? with 5 disks?  
    * 3 - 7 moves
    * 4 - 15 moves
    * 5 - 31 moves

* What is the runtime of your algorithm?  
O(2^n), because as the input is increased the runtime is increasing exponentially.
## 12. Iterative version
Solve the drills 1 - 7 from your previous checkpoint (Recursion) iteratively.

1. Counting Sheep  
  
Recursive:
```
const countingSheep = (count, array) => {
    let lines = array || [];
    //Base case
    if (count <= 0) {
        lines.push(`All sheep jumped over the fence`)
        return lines.join('\n');
    }
    //General Case
    lines.push(`${count}: Another sheep jumps over the fence`)
    return countingSheep(--count, lines)
    
}
```
Iterative:
```
const countingSheep = count => {
    let lines = [];
    for (count; count > 0; count--) {
        lines.push(`${count}: Another sheep jumps over the fence`)
    }
    lines.push(`All sheep jumped over the fence`)
    return lines.join('\n');
    
}
```
2. Power Calculator 
   
Recursive:
```
const powerCalculator = (base, exponent) => {
    //Invalid case
    if(exponent < 0) {
        return `exponent should be >= 0`
    }
    //If exponent is equal to 0
    if(exponent === 0) {
        return 1
    }

    //Base Case
    if(exponent === 1) {
        return base
    }

    //General Case
    return base * powerCalculator(base, --exponent)
}
```
Iterative:
```
const powerCalculator = (base, exponent) => {
    if(exponent < 0) {
        return `exponent should be >= 0`
    }
    if(exponent === 0) {
        return 1
    }

    if(exponent === 1) {
        return base
    }
    let result = base
    for(let i = 2; i <= exponent; i++) {
        result*=base
    }
    return result
}
```
3. Reverse String 
   
Recursive:
```
const reverseString = string => {
    if(string === '') return '';
    return reverseString(string.substr(1)) + string.charAt(0);
}
```
Iterative:
```
const reverseString = string => {
    let strArr = string.split('');
    let returnStr = '';
    for(let i = strArr.length -1; i >= 0; i--) {
        returnStr += strArr[i];
    }
    return returnStr;
}
```
4. nth Triangular Number  
  
Recursive:
```
const nthTriangularNum = (num) => {
    //Invalid Case
    if(num <= 0) {
        return console.log(`Number must be a positive integer`);
    }

    //Base Case
    if(num <= 1) {
        return num;
    }

    //General Case
    return num + nthTriangularNum(num - 1);
}
```
Iterative:
```
const nthTriangularNum = (num) => {
    if(num <= 0) {
        return console.log(`Number must be a positive integer`);
    }
    let resultNum = 0;
    for(let i = num; i > 0; i--) {
        resultNum += i;
    }
    return resultNum;
}
```
5. String Splitter  
  
Recursive:
```
const stringSplitter = (string, delimiter, arr) => {
    let str = string.trim();
    let words = arr || [];
    let index = str.indexOf(delimiter);

    //Base Case
    if(index < 0) {
        words.push(str);
        return words;
    }

    //General Case
    words.push(str.substr(0, index));
    return stringSplitter(str.slice(index + 1), delimiter, words);
}
```
Iterative:
```
const stringSplitter = (string, delimiter) => {
    let str = string.trim();
    let words = [];
    let index = str.indexOf(delimiter);

    if(index < 0) {
        words.push(str);
        return words;
    }

    while(index >= 0) {
        words.push(str.substr(0, index + 1));
        str = str.slice(index + 1);
        index = str.indexOf(delimiter);
    }
    words.push(str);
    return words;
}
```
6. Fibonacci  
  
Recursive:
```
const fibonacci = (num, prevVal) => {
    prevVal = prevVal || {}
    //Base Case
    if(prevVal[num]){
        return prevVal[num];
    }

    if(num <= 0){
        return 0;
    }
    if(num === 1) {
        return 1;
    }

    //General Case

    return prevVal[num] = fibonacci(num - 1, prevVal) + fibonacci(num - 2, prevVal);
}
```
Iterative:
```
const fibonacci = (num) => {
    result = [];
    for(let i = 1; i <= num; i++) {
        if(i === 1) {
            result.push(0);
        } 
        else if(i === 2) {
            result.push(1);
        }
        else {
            result.push(result[i - 2] + result[i - 3]);
        }
    }
    return result;
}
```
7. Factorial  
  
Recursive:
```
const factorialNum = num => {
// Base case
if(num <= 1) {
    return num;
}

//General Case
return num * factorialNum(num - 1);
}
```
Iterative:
```
const factorialNum = num => {
if(num <= 1) {
    return num
}
let result = num;
for(let i = num - 1; i > 0; i--) {
    result *= i;
}
return result;
```

## 13. Recursive Big O
Take your solutions from the recursive exercises that you completed in the previous checkpoint and identify the time complexities (big O) of each of them.

*Solution* :  
1. Counting Sheep - O(n)
2. Power Calculator - O(n)
3. Reverse String - O(n)
4. nth Triangular Number - O(n)
5. String Splitter - O(n)
6. Fibonacci - O(n)
7. Factorial - O(n)
8. Find a way out of the maze - O(3^n)
9. Find all of the ways out of the maze - O(3^n)
10. Anagrams - O(n^2)
11. Organization Chart - O(n^2)


## 14. Iterative Big O
Take your solutions from the iterative exercises today and identify the time complexities (big O) of each of them.

1. Counting Sheep - O(n)
2. Power Calculator - O(n)
3. Reverse String - O(n)
4. nth Triangular Number - O(n)
5. String Splitter - O(n)
6. Fibonacci - O(n)
7. Factorial - O(n)
8. Tower of Hanoi - O(2^n)


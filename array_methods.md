#### 1. Common Array Methods Cheatsheet: 

```
// Mutating
push()      // Insert an element at the end
pop()       // Remove an element from the end
unshift()   // Inserts an element in the beginning
shift()     // Remove first element
includes() // checks whether a certain element is present in the array. It returns true or false.
// Iterating
forEach()   // Iterates an array
filter()    // Iterates an array and result is filtered array(pushes value that satsfies condition)
map()       // Iterates an array and result is new array (pushes return value)
reduce()    // "Reduces" the array into single value (accumulator)
every()    // iterates and checks if all elements in the array passes the test. return false if one fails
some()    // iterates and checks at least one element in the array passes the test. terminates loop if atleast one passes and return true.
find()  // The find() method returns the value of the first element in the provided array that satisfies the provided testing function. If no values satisfy the testing function, undefined is returned.
// Others
slice()     // Returns desired elements in a new array
concat()    // Append one or more arrays with given array
```

```javascript
const arr = [1,2,3,4,5,6,7,8,9]

arr.push(10)
console.log(arr)
//expected output: [1,2,3,4,5,6,7,8,9,10]

arr.pop()
console.log(arr)
//expected output: [1,2,3,4,5,6,7,8]

arr.unshift(0,14)
console.log(arr)
//expected output: [0,14,1,2,3,4,5,6,7,8,9]

arr.shift()
console.log(arr)
//expected output: [2,3,4,5,6,7,8,9]

// Array iteration methods:

const words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];

const resultFilter = words.filter(word => word.length > 6);
const resultFind = words.find(word => word.length > 6);
const resultMap = words.map(word => word.length > 6);
const resultEvery = words.every(word => word.length > 6);
const resultSome = words.some(word => word.length > 6);
const resultReduce = words.reduce(word => word.length > 6);
console.log({resultFilter,resultFind,resultMap,resultEvery,resultSome,resultReduce})
/*
 expected output: Object { 
  resultFilter: Array ["exuberant", "destruction", "present"],
  resultFind: "exuberant",
  resultMap: Array [false, false, false, true, true, true],
  resultEvery: false,
  resultSome: true,
  resultReduce: false 
}
*/
const arr = [
  { name: "A", quantity: 1, price: 20 },
  { name: "B", quantity: 2, price: 40 },
  { name: "C", quantity: 3, price: 60 },
  { name: "D", quantity: 4, price: 80 }
];
const test = arr.reduce((acc,curr) => acc + (curr.quantity * curr.price),0);
console.log(test);
// expected output: 600

const array1 = ['a', 'b', 'c'];
// *for of  for object/array properties* only for iterables array/object
for (const element of array1) {
  console.log(element);
}

// expected output: "a"
// expected output: "b"
// expected output: "c"
// *for in  for object/array keys* --> index non iterable aswell. works for like single object
for (const element in array1) {
  console.log(element);
}

// expected output: "0"
// expected output: "1"
// expected output: "2"

const object = [{ a: 1, b: 2, c: 3 },{ a: 4, b: 5, c: 6 }];

for (const record of records) {
  console.log(record)
}

// expected output:
// Object { a: 1, b: 2, c: 3 }
// Object { a: 4, b: 5, c: 6 }

const object = [{ a: 1, b: 2, c: 3 },{ a: 4, b: 5, c: 6 }];

for (const [i, record] in records.entries()) {
  console.log(record)
}
// expected output:
// "0"
// "1"

const records = [
  {
    a: 'somestring',
    b: 42
  }, {
    a: 'somestring',
    b: 43
  },
  {
    a: 'somestring',
    b: 44
  }
];

for (const [key, value] of Object.entries(records)) {
  console.log(`${key}: ${value.b}`);
}
// expected output
// "0: 42"
// "1: 43"
// "2: 44"
```

#### Fill array with values(strings, numbers or even objects):

```javascript
const array = Array(5).fill(0);

console.log(array);
// expected output: [0, 0, 0, 0, 0]

const array1 = Array(5).fill('a');
console.log(array1);
// expected output: ['a', 'a', 'a', 'a', 'a']


// syntax: array.fill(value, start, end)
// fills array from position 1-3 with b: 
array1.fill('b', 1, 3);
console.log(array1);
// expected output: ['a', 'b', 'b', 'b', 'a']

// fill array with objects:

const data = Array.from({ length:5 }, () => ({value:2}));
console.log(data);
// expected output: [{value: 2}, {value: 2}, {value: 2}, {value: 2}, {value: 2}]

// or with fill() and map() together:
const data0 = Array(3).fill().map(item => ({ value: 2 }));
console.log(data0);
// expected output: [{value: 2}, {value: 2}, {value: 2}]

// referenced type be aware
const data1 = Array(5).fill({value:2});
console.log(data1);
// expected output: [{value: 2}, {value: 2}, {value: 2}, {value: 2}, {value: 2}]

//changing one refernced value changes all others
data1[0].value = 3;
console.log(data1);
// expected output: [{value: 3}, {value: 3}, {value: 3}, {value: 3}, {value: 3}]
```
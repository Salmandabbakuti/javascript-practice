##### 1. Multiple '&&' checks:

```javascript
// long hand
const data = { a: 22, b: 34, c: 21, d: 44, e: 12, e: 10 }
if (data.a && data.b && data.c && data.d) {
  // do something
}

// shorthand

if (['a', 'b', 'c', 'd'].every((x) => x in data)) {
  // do something
}
```

##### 2. Multiple '||' checks:

```javascript
//longhand
if (a === 'test' || a === 'net' || a === 'tom') {
  // do something
}

//shorthand
if (['test', 'net', 'tom'].includes(a)) {
  // do something
}
```

##### 3. Multiple '||' checks for different properties

```javascript
//longhand
const data = { a: 22, b: 33, c: 12, d: 20 };
if (data.a === 22 || data.b === 22 || data.c === 22) {
  // do something
}


// shorthand
if (['a', 'b', 'c'].some((x) => data[x] === 22)) {
  // do something
}
```
##### 4. Join Array of Fields:

```javascript

const a = [
  {names:['Ravi', 'Sai','Kiran']},
  {names:['Suma', 'Sandy','Shreya']}
  ]
let names;
a.forEach((data)=> names += `${data.names.join(', ')}, `)
console.log(names)

// result: 'Ravi', 'Sai','Kiran','Suma', 'Sandy','Shreya', ==> remove ending comma by substr method
```
#### 5. Null, Empty, Undefined Checks:

```javascript
// Longhand version
if(productName !== undefined || productName !== "" || productName !== null){
    console.log(productName)
}
  
// Shorthand version
if(productName){
    console.log(productName)
}
```

#### 6. Implicit Return:

```javascript
const getProductPrice = (price,quantity) => quantity * price;
const result = getProductPrice(12,5)
// result : 60

```

#### 7. Multiple If/switch cases:

```javascript
//longhand

if(a ==='a'){
  //doA()
}
else if(a==='b'){
  //doB()
}else if(a==='c'){
  //doC();
}

const a = 'a';
switch (a) {
  case 'a':
    //doA();
  case 'b':
    //doB()
  case 'c':
    //doC()

  // shorthand

  const cases = {
    a: doA
    b:doB
    c:doC
  }
  const doA = (val1,val2)=> { 
    // doA code
  }
  return cases[a](val1,val2); // you can also pass args like this
```

#### 8. Optional Chaining:

```javascript
//longhand
if(person&& person.address&& person.address.city){
  // console.log(person.address.city)
}

// shorthand
(person?.address?.city){
  //console.log(person.address.city) // null errors will be handled perfectly here
}
```
#### 9. declaring multiple variables once:

```javascript

// longhand
let a = 10;
let b= 10;
let c = 10;

//shorthand
let a, b, c = 10;
let [a, b, c] = [10, 20, 30 ]; // assigning different values
```

#### 10. Spread Utilities:

```javascript

// Merging arrays, objects
const one = [1, 2, 3];
const two = [4, 5, 6];
objectA = { a:22, b:34};
const objectB = {c:28, d:30};

// Longhand
const newArray = one.concat(two);
const newObject = Object.assign(objectA, objectB);
// Shorthand
const newArray = [...one, ...two];
const newObject = {...objectA, ...objectB}

// destructuring
const {a, ...restObject} = newObject
// expected output: a:22, {b:34, c:28, d:30}
```
#### 11. Object property assignment: 

```javascript

const name = "John",
  city = "NY",
  age = 25;

// Longhand
const person = { name: name, city: city, age: age };

// Shorthand
const person = { name, city, age };
```

#### 12. Mandatory Parameters:

```javascript
function Greet(message) {
  if (message === undefined) {
    throw new Error("Missing parameter!");
  }
  // do some operations here
  return message;
}

mandatory = () => {
  throw new Error("Missing parameter!");
};

Greet = (message = mandatory()) => {
  // do some operations here
  return message;
};
```

#### 13. Nullish Coalescing(??)

```javascript
let a
let b = a ?? "Nothing found"
console.log(b)
// expected output: "Nothing found"

let a = 12
let b = a ?? "Nothing found"
console.log(b)
// expected output: 12
```

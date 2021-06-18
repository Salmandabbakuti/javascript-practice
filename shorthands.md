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

##### 2. multiple '||' checks:

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
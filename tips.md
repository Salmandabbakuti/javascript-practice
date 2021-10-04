#### 1. Coverting Array to Object:

```javascript
// from 
['firstName' ,'lastName','recordSource']

// to 
{firstname:'First Name', lastname:'Last Name', recordsource:'Record Source'}


const data = ['firstName', 'lastName', 'recordSource'];
const dataObject = {};

const capitalizeText = (text) => {
  const result = text.replace(/([A-Z])/g, ' $1');
  return result.charAt(0).toUpperCase() + result.slice(1);
};
data.forEach(item => {
  dataObject[item.toLowerCase()] = stringToCapitalised(item);
});
console.log(dataObject);

//result: {"firstname": "First Name", "lastname": "Last Name", "recordsource": "Record Source"}
```

#### 2. Find Duplicates in Arry:

```javascript
  const data = [22, 31, 34, 33, 71, 33, 22, 11, 71, 'aa','bb','aa']
  let data1 = [...data].sort() // cloning array so original won't be affected. sorting makes duplicates adjusent.
  let results = [];
  data1.forEach((el, i) => {
    if (data1[i + 1] == data1[i]) {
      results.push(data1[i]);
    }
  })
  console.log(results);
// expected: Array [22, 33, 71, "aa"]
```
#### 3. Performance Test: 

```javascript
const doSomething = () => {
  // do something code
}
const t0 = performance.now();
doSomething();
const t1 = performance.now();
console.log(`Call to doSomething took ${t1 - t0} milliseconds.`);
```
#### 4. Emptying Array: 

```javascript
const arr = ['a','b','c','d','e','f'];
arr.length = 0;
console.log(arr)
// expected output: Array []
```

#### 5. Customizing Field Names dynamically (Lookup model):

```javascript
const fieldNames = {
  firstname:'First Name',
  ssnorsin: 'SSN/SIN'
}
const selectedFields = ['firstname', 'lastname', 'ssnorsin']
console.log('initial selected fields-->', selectedFields);
selectedFields.forEach((f,i)=> {
  selectedFields[i] = fieldNames[f]? fieldNames[f]: f ;
})
console.log('final selected fields-->', selectedFields);

// expected output:
// initial selected fields--> Array ["firstname", "lastname", "ssnorsin"]
// final selected fields--> Array ["First Name", "lastname", "SSN/SIN"]
```

#### 6. Filter out false values from array:

```javascript
const data = [1, 0, false, "", 2, NaN, 0n, null, 3, undefined, 4]
const filteredData = data.filter(Boolean)
console.log(filteredData) 
//expected output: [1, 2, 3, 4]
```

#### 7. Flattening the array:

```javascript
const array = [123, 500, [1, 2, [34, 56, 67, [234, 1245], 900]], 845, [30257]]
console.log(array.flat(Infinity)) // flatten array of array with infinity
//expected output: [123, 500, 1, 2, 34, 56, 67, 234, 1245, 900, 845, 30257]
```

#### 8. Remove duplicate values from Array:

```javascript
const data = [0, 1, 2, 1, 3, 2, 4, 3, 5, 4, 6, 6, 7, 7, 8, 8, 9, 0, 'Ann', 'Ann', 'Lori', 'Lori', false, false, undefined, undefined, null, null];
const unique = [...new Set(data)];
console.log(unique);
// expected output: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, "Ann", "Lori", false, undefined, null]
```
#### 9. Count all occurances of object property value in array of objects:

```javascript
// from
const array = [
{type:'A', impact:'serious'},
{type:'B', impact:'serious'},
{type:'A', impact:'moderate'},
{type:'M', impact:'serious'},
{type:'A', impact:'low'},
{type:'A', impact:'low'},
{type:'A', impact:'critical'},
{type:'N', impact:'serious'},
{type:'A', impact:'critical'},
{type:'D', impact:'critical'},
{type:'D', impact:'high'}
]

//to
{ serious: 4, moderate: 1, low: 2, critical: 3, high: 1 }

// syntax: array.reduce(previousValue, currentValue) => { ... }, initialValue)
const result = array.reduce((a, {impact}) => {
  a[impact] = a[impact] || 0
  a[impact]++
  return a;
}, {});

console.log(result);
// expected output: { serious: 4, moderate: 1, low: 2, critical: 3, high: 1 }
```
#### 10. Generate Ids based on timestamp:

```javascript
const id = new Date().toISOString().replace(/[^0-9]/gi, '') // deletes every chracter except digits from iso time string. possible characters in ISO String ie "., -, T, Z, :"
console.log(id);
// expected output: "20211004092101782" //Id in YYYYMMDDHHMMSSsss format. useful for filenames, uids
```

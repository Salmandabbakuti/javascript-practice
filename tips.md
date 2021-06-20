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
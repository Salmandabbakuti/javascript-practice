### RegEx Essentials

```
1. exec
2. match
3. test
4. toString()
```
#### The RegExp class
```javascript

// new RegExp(expressionPattern, flag)
const re = new RegExp("\\d", "g");

const result = "Aabbccdd".match(/a/gi);
console.log(result)
//expected output: Array ["A", "a"]

const result = "Aabbccdd".match(/[abc]/gi); // match any of a,b,c globally and insensitive
const result = "Aabbccdd".match(/[^abc]/gi); // dont match any of a,b,c globally and insensitive. returns all others


```


#### 1. includes: 

```javascript
const sentence = "I'm looking for my cats";
console.log(sentence.includes('cats')); 
// output : true

```
#### 2. trim:

```javascript
const greeting = '   Hello to the world   ';
console.log(greeting.trim());
// expected output: "Hello to the world";
```

#### 3. concat:

```javascript
onst str1 = 'Hello';
const str2 = 'dear reader';

console.log(str1.concat(' ', str2));
// expected output: "Hello dear reader"

console.log(str2.concat(', ', str1));
// expected output: "dear reader, Hello"
```
#### 4. substr/substring:

```javascript
const str = 'backend world, ';

console.log(str.substr(0, 7));
// expected output: "backend"  //   substr(from, length)
console.log(str.substr(8)); // remove first 8 letters and give the rest
// expected output: "world, "
console.log(str.substr(0, str.length - 2))
// expected output: "backend world"

//Note: substring(from, index) // substring and substr are same but second argument of substr is length where thisone has index to slice
```
#### 5. slice:

```javascript
const str = 'Lazy loading enhances your web app performances';

console.log(str.slice(0));
// expected output: "Lazy loading enhances your web app performances"

console.log(str.slice(0, 12));
// expected output: "Lazy loading"

console.log(str.slice(-34));
// expected output: "enhances your web app performances"

console.log(str.slice(-20, -13));
// expected output: "web app"
```
#### 6. split:

```javascript
const str = "Hello.Developers How are you doing?";

console.log(str.split('.'));
// expected output: Array ["Hello", "Developers How are you doing?"]
console.log(str.split(' '));
// expected output: Array ["Hello.Developers", "How", "are", "you", "doing?"]
console.log(str.split(''));
// expected output: Array ["H", "e", "l", "l", "o", ".", "D", "e", "v", "e", "l", "o", "p", "e", "r", "s", " ", "H", "o", "w", " ", "a", "r", "e", " ", "y", "o", "u", " ", "d", "o", "i", "n", "g", "?"]
```
#### 7. match:

```javascript
const text = 'Discover, learn and keep learning...';
//Get upper cases regex
const regex = /[A-Z]/g;
console.log(text.match(regex));
//expected ouptput: Array ["D"]
```
#### 8. replace:
```javascript
const text = 'Welcome to the front, place for front-end trends and techniques. Welcome';

console.log(text.replace('Welcome', 'Welcome dear reader'));
// expected output: "Welcome dear reader to the front, place for front-end trends and techniques"
console.log(text.replaceAll('Welcome', 'Welcome dear reader'));
// expected output: "Welcome dear reader to the front, place for front-end trends and techniques. Welcome dear reader"
```
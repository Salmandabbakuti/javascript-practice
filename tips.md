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
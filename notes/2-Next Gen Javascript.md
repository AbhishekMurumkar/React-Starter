# Next Generation Javascript

(that below notations will work with babel as javascript pre-processor)

## 1. [LET & VAR](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let) & [CONST](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const)

* let allows you to declare variables that are limited to the scope of a block statement, or expression on which it is used, 
* unlike the var keyword, which declares a variable globally, or locally to an entire function regardless of block scope. 
* The other difference between var and let is that the latter is initialized to a value only when a parser evaluates it

---

## 2. Arrow function

Normal function

```javascript
//typ1
function myfunc{

}
//type 2
//if we have only one arguement
function myfunc2(p1){

}
//type 3
function myfunc3(p1,p2,p3){

}

// suppose in our function body we have only one return statement , like below
function mul2(num){
    return num*2;
}
```

Arrow Equalent

```javascript
// type1
()=>{
}
//type 2
//if we have only one arguement
p1=>(

)
//type 3
(p1,p2,p3)=>{

}
// suppose in our function body we have only one return statement , like below
num=>num*2;
```

---

## 3. exports and imports to support modularization of code snippets:

3.1) to export something

```javascript
export default object_or_variable_or_const_name;
```

example:

```javascript
// 1.
const person = { name:'Abhi' }
export default person [let the content be present in a file named as person.js]
// 2.
export const clean = ()=>{..}
export const baseData = 10;[let the content be present in a file named as utility.js]
```

3.2) to import something

```javascript
import object_or_variable_or_const_name from './path/of/export/js/file'
```

example:

```javascript
// 1.
import person from './person.js';
import prs from './person.js'; //no matter at what name we import person.js we always end up in importing the person object with name as 'Abhi' value as sub object since the presence of default keyword on the export in person.js . Thus person and prs denote the same person object

// 2.
import { baseData } from './utility.js';
import { clear } from './utility.js'; //These are called the named exports since we exporting specfic parts of the file via their name
```

---

## 4. Classes

Note the methods written above short notations cannot be ran by plain javascript hence we need the babel to run it

### IN ES 5,

```javascript
class Human{
    // this is made in ES 5
    constructor(){
        this.gender="Male";
    }
    // however you can initialize value directly in class from ES6
    gender="Male";
}
class Person extends Human {//inheritance
    //this is in ES 5
    constructor(){
        super(); // this is mandatory whenever we have interitance
        this.name='Abhi'
    }
    printName(){
        console.log(this.name)
        console.log(this.gender);// we cannot access gender without calling super()
    }
}
const myPerson = new Person();
// executing methods
myPerson.printName();
```

output

```sh
"Abhi"
"Male"
```

### IN ES 6

```javascript
class Human{
    gender="Male";
}
class Person extends Human {//inheritance
    name="Abhi"
    printName=()=>{
        console.log(this.name);
        console.log(this.gender); // we can access gender without calling super()
    }
}
//instantiating Person
const myPerson = new Person();
// executing methods
myPerson.printName();
```

output

```sh
"Abhi"
"Male"
```

---

## 5. Spread and Rest Operator

### 5.1 SPREAD:

Used to split up array or dom properties. Mainly used to modify content in existing one and assign it to same variable but with new reference.

 Example

```javascript
//this spread tends to add the elements 1,2 to old array and place it in the newarr variable
const newarr = [...oldarr,1,2]
// this is same as above where we tend to add property named newProp with value 'value' to an existing object 'oldObj' and thus point new object to 'newProp'
//( if newProp named property already exists in oldObj then its value is being overriden with new value 'value')
const newProp = {...oldObj,newProp:value}

//example for spread operator
let person={
  'name':"abhishek"
};

let new_person={
  ...person,
  age:23
};
console.log(new_person);
```

### 5.2 REST

used to merge a list of arguements into an array ```function numbers(...args){..}```

Example

```javascript
function add(...args){
  let sum=0;
  console.log(args);
  for(let i in args){
     sum+=args[i];
  }
  console.log('total sum='+sum);
}
add(1,2,3);
```

---

## 6. Destructuring:

* extract the array elements or dom properties and store them in a variable
* difference between spread and destructuring is that
	* spread operator will takes elements or properties and distributes in the new variable
	* where as destructuring is allowed for specific property or element

Array Destructuring:

```javascript
[a,b]=[1,2] //thus a=1 and b=2
[a,,c]=[1,2,3]//thus a=1 and c=3
```

Object Destructuting:

```javascript
{name,age}={name:'Abhi',age:'23'}
//thus name='Abhi' and age='23'
```

## 7. Reference and Primitive Type Refreshers:

### 7.1 In Primitive

```javascript
let num=2;
let ref_num=num;
num=1;
console.log('primitive real='+num+' ref = '+ref_num);
```

output: ```primitive real=1 and ref=2```

### 7.2 In Non-Primitive

```javascript
let obj = {
  name:'abhi'
}
let ref_obj=obj;
obj.name='abhishek';
console.log('non primitive real');
console.log(obj);
console.log('non primitive ref');
console.log(ref_obj);
```

output:

```javascript
"non primitive real"
Object {
  name: "abhishek"
}
"non primitive ref"
Object {
  name: "abhishek"
}
```

This is only to show that non-primitive types assign value by memory location but not by copying the reference of memory locations as primitive types. **_The immutability applies to both arrays and objects because they are non-primitive type objects_**

Thus to get behaviour of the primitive types to non-primitive ones we need to

```javascript
let obj = {
  name:'abhi'
}
let ref_obj={...obj}
obj.name='abhishek';
console.log('non primitive real');
console.log(obj);
console.log('non primitive ref');
console.log(ref_obj);
```

output:

```javascript
"non primitive real"
Object {
  name: "abhishek"
}
"non primitive ref"
Object {
  name: "abhi"
}
```

---

## 8. Array functions

(also works without babel)
* [map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
* [find()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find)
* [findIndex()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex)
* [filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
* [reduce()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce?v=b)
* [concat()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat?v=b)
* [slice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice)
* [splice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)

Next=> [React-Quickstart](./3-ReactQuickStart.md)
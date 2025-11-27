# JavaScript tarixi va evolyutsiyasi: Classic JS dan ES6+ gacha

## JavaScript yaratilishi (1995)

JavaScript 1995-yilda Brendan Eich tomonidan atigi **10 kun** ichida yaratilgan. Dastlab "Mocha", keyin "LiveScript" deb atalgan, nihoyat "JavaScript" nomini oldi (Java bilan hech qanday aloqasi yo'q edi, bu faqat marketing strategiyasi edi).

## ECMAScript standarti

1997-yilda JavaScript standartlashtirildi va **ECMAScript** (ES) nomi bilan rasmiy spetsifikatsiya yaratildi. ECMA International tomonidan boshqariladi.

---

## Classic JavaScript (ES3/ES5 davri: 1999-2009)

### ES3 (1999) - Birinchi keng qo'llanilgan versiya

```javascript
// O'zgaruvchilar faqat var bilan
var name = "John";
var age = 25;

// Funksiyalar
function greet(name) {
  return "Hello, " + name;
}

// Obyektlar
var person = {
  name: "John",
  age: 25,
  greet: function() {
    return "Hello, " + this.name;
  }
};

// Massivlar
var numbers = [1, 2, 3, 4, 5];

// Sikllar
for (var i = 0; i < numbers.length; i++) {
  console.log(numbers[i]);
}

// Shartlar
if (age >= 18) {
  console.log("Adult");
} else {
  console.log("Minor");
}
```

### ES5 (2009) - Katta yangilanish

ES5 bir qancha muhim xususiyatlar qo'shdi:

```javascript
// Strict mode
"use strict";

// Array metodlari
var numbers = [1, 2, 3, 4, 5];

// forEach
numbers.forEach(function(num) {
  console.log(num);
});

// map
var doubled = numbers.map(function(num) {
  return num * 2;
});

// filter
var evens = numbers.filter(function(num) {
  return num % 2 === 0;
});

// reduce
var sum = numbers.reduce(function(acc, num) {
  return acc + num;
}, 0);

// Object metodlari
var obj = Object.create(null);
Object.keys(person);
Object.defineProperty(obj, 'name', {
  value: 'John',
  writable: false,
  enumerable: true
});

// JSON support
var jsonString = JSON.stringify(person);
var parsedObj = JSON.parse(jsonString);

// Function.prototype.bind
var boundFunc = greet.bind(person);
```

### Classic JS muammolari

1. **var ning muammolari**: Function scope, hoisting, redeclaration
2. **Callback hell**: Asynchronous kod yozishda qiyinchiliklar
3. **this konteksti**: Noaniq va xatoga moyil
4. **String concatenation**: Ko'p qatorli stringlar bilan ishlash qiyin
5. **Inheritance**: Prototype-based inheritance murakkab
6. **Module tizimi yo'q**: Global scope iflosligi

---

## ES6/ES2015 - Katta inqilob 🚀

2015-yilda JavaScript tarixidagi eng katta yangilanish chiqdi. Bu versiya tilni butunlay o'zgartirdi.

### 1. let va const

```javascript
// Block scope
{
  let x = 10;
  const y = 20;
  var z = 30;
}
// console.log(x); // Error
// console.log(y); // Error
console.log(z); // 30 - var hali ham ishlaydi

// const - o'zgarmas
const PI = 3.14;
// PI = 3.15; // Error

// let - o'zgaruvchan
let count = 0;
count++; // OK

// Hoisting farqi
console.log(varVariable); // undefined
// console.log(letVariable); // ReferenceError (Temporal Dead Zone)
var varVariable = 'var';
let letVariable = 'let';
```

### 2. Arrow Functions

```javascript
// Old way
var add = function(a, b) {
  return a + b;
};

// Arrow function
const add = (a, b) => a + b;

// Bir parametr - qavslar ixtiyoriy
const square = x => x * x;

// Ko'p qatorli
const greet = name => {
  const message = `Hello, ${name}!`;
  return message;
};

// this konteksti: arrow function o'z this yaratmaydi
function Timer() {
  this.seconds = 0;
  
  // Old way - this ni saqlash kerak edi
  var self = this;
  setInterval(function() {
    self.seconds++;
  }, 1000);
  
  // Arrow function - this avtomatik
  setInterval(() => {
    this.seconds++;
  }, 1000);
}
```

### 3. Template Literals (Backticks)

```javascript
// Old way
var name = "John";
var age = 25;
var message = "Hello, " + name + "! You are " + age + " years old.";

// Template literals
const message = `Hello, ${name}! You are ${age} years old.`;

// Ko'p qatorli stringlar
const html = `
  <div>
    <h1>${title}</h1>
    <p>${content}</p>
  </div>
`;

// Expression ichida
const price = 100;
const tax = 0.15;
console.log(`Total: $${price * (1 + tax)}`);

// Tagged templates
function highlight(strings, ...values) {
  return strings.reduce((result, str, i) => {
    return result + str + (values[i] ? `<mark>${values[i]}</mark>` : '');
  }, '');
}

const result = highlight`Price is ${price} with tax ${tax}`;
```

### 4. Destructuring

```javascript
// Array destructuring
const numbers = [1, 2, 3, 4, 5];

// Old way
var first = numbers[0];
var second = numbers[1];

// New way
const [first, second, ...rest] = numbers;
console.log(first); // 1
console.log(second); // 2
console.log(rest); // [3, 4, 5]

// Object destructuring
const person = {
  name: "John",
  age: 25,
  address: {
    city: "New York",
    country: "USA"
  }
};

// Old way
var name = person.name;
var age = person.age;

// New way
const { name, age, address: { city } } = person;

// Default values
const { email = "no-email@example.com" } = person;

// Renaming
const { name: personName, age: personAge } = person;

// Function parametrlarida
function greet({ name, age }) {
  return `${name} is ${age} years old`;
}

greet(person);
```

### 5. Default Parameters

```javascript
// Old way
function greet(name, greeting) {
  name = name || "Guest";
  greeting = greeting || "Hello";
  return greeting + ", " + name;
}

// New way
function greet(name = "Guest", greeting = "Hello") {
  return `${greeting}, ${name}`;
}

// Expression sifatida
function createUser(name, id = Date.now()) {
  return { name, id };
}

// Oldingi parametrlardan foydalanish
function calculate(x, y = x * 2) {
  return x + y;
}
```

### 6. Rest va Spread Operators

```javascript
// Rest operator - parametrlarni massivga yig'ish
function sum(...numbers) {
  return numbers.reduce((acc, num) => acc + num, 0);
}

sum(1, 2, 3, 4, 5); // 15

// Spread operator - massivni yoyish
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];

// Old way
var combined = arr1.concat(arr2);

// New way
const combined = [...arr1, ...arr2];
const withExtra = [0, ...arr1, 3.5, ...arr2, 7];

// Obyektlar bilan
const person = { name: "John", age: 25 };
const employee = {
  ...person,
  company: "ABC Corp",
  salary: 50000
};

// Copy qilish
const personCopy = { ...person };
const arrCopy = [...arr1];

// Function argumentlari
const numbers = [1, 2, 3, 4, 5];
Math.max(...numbers); // 5
```

### 7. Object Enhancements

```javascript
const name = "John";
const age = 25;

// Old way
var person = {
  name: name,
  age: age,
  greet: function() {
    return "Hello, " + this.name;
  }
};

// Property shorthand
const person = {
  name,
  age,
  // Method shorthand
  greet() {
    return `Hello, ${this.name}`;
  }
};

// Computed property names
const propName = "dynamicProp";
const obj = {
  [propName]: "value",
  ["computed" + "Name"]: "another value"
};

// Object.assign
const defaults = { theme: "light", language: "en" };
const userPrefs = { language: "uz" };
const config = Object.assign({}, defaults, userPrefs);

// Object methods (ES2017+)
Object.entries(person); // [["name", "John"], ["age", 25]]
Object.values(person); // ["John", 25]
```

### 8. Classes

```javascript
// Old way - Constructor functions
function Person(name, age) {
  this.name = name;
  this.age = age;
}

Person.prototype.greet = function() {
  return "Hello, " + this.name;
};

// New way - Classes
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
  
  greet() {
    return `Hello, ${this.name}`;
  }
  
  // Static methods
  static create(name, age) {
    return new Person(name, age);
  }
  
  // Getters/Setters
  get info() {
    return `${this.name} (${this.age})`;
  }
  
  set info(value) {
    const [name, age] = value.split(',');
    this.name = name;
    this.age = parseInt(age);
  }
}

// Inheritance
class Employee extends Person {
  constructor(name, age, company) {
    super(name, age); // Parent constructor
    this.company = company;
  }
  
  greet() {
    return `${super.greet()}, I work at ${this.company}`;
  }
}

const emp = new Employee("John", 25, "ABC Corp");
```

### 9. Modules (Import/Export)

```javascript
// Old way - Global scope yoki AMD/CommonJS
// user.js
window.User = function(name) {
  this.name = name;
};

// main.js
var user = new window.User("John");

// ES6 Modules
// user.js
export class User {
  constructor(name) {
    this.name = name;
  }
}

export const DEFAULT_NAME = "Guest";

export function createUser(name) {
  return new User(name);
}

// Default export
export default User;

// main.js
import User, { DEFAULT_NAME, createUser } from './user.js';
// yoki
import * as UserModule from './user.js';

// Named imports
import { User, createUser } from './user.js';

// Aliasing
import { User as UserClass } from './user.js';
```

### 10. Promises

```javascript
// Old way - Callback hell
function getData(callback) {
  setTimeout(function() {
    callback(null, { id: 1 });
  }, 1000);
}

getData(function(err, data) {
  if (err) {
    console.error(err);
  } else {
    getUser(data.id, function(err, user) {
      if (err) {
        console.error(err);
      } else {
        getPosts(user.id, function(err, posts) {
          // Va hokazo...
        });
      }
    });
  }
});

// Promises
function getData() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve({ id: 1 });
    }, 1000);
  });
}

getData()
  .then(data => getUser(data.id))
  .then(user => getPosts(user.id))
  .then(posts => console.log(posts))
  .catch(error => console.error(error))
  .finally(() => console.log('Done'));

// Promise.all - parallel execution
Promise.all([promise1, promise2, promise3])
  .then(([result1, result2, result3]) => {
    console.log(result1, result2, result3);
  });

// Promise.race - birinchi tugagani
Promise.race([promise1, promise2])
  .then(result => console.log(result));
```

### 11. Iterators va Generators

```javascript
// Iterator
const iterable = {
  data: [1, 2, 3, 4, 5],
  [Symbol.iterator]() {
    let index = 0;
    return {
      next: () => {
        if (index < this.data.length) {
          return { value: this.data[index++], done: false };
        }
        return { done: true };
      }
    };
  }
};

for (const value of iterable) {
  console.log(value);
}

// Generators
function* numberGenerator() {
  yield 1;
  yield 2;
  yield 3;
}

const gen = numberGenerator();
console.log(gen.next()); // { value: 1, done: false }
console.log(gen.next()); // { value: 2, done: false }
console.log(gen.next()); // { value: 3, done: false }
console.log(gen.next()); // { done: true }

// Infinite generator
function* infiniteSequence() {
  let i = 0;
  while (true) {
    yield i++;
  }
}

// Generator bilan async operations
function* fetchUserData() {
  const user = yield fetch('/api/user');
  const posts = yield fetch(`/api/posts/${user.id}`);
  return posts;
}
```

### 12. Symbols

```javascript
// Unique identifiers
const sym1 = Symbol('description');
const sym2 = Symbol('description');
console.log(sym1 === sym2); // false

// Object property sifatida
const ID = Symbol('id');
const person = {
  name: "John",
  [ID]: 12345
};

console.log(person[ID]); // 12345
console.log(Object.keys(person)); // ['name'] - Symbol ko'rinmaydi

// Well-known symbols
const myIterable = {
  data: [1, 2, 3],
  [Symbol.iterator]() {
    // ...
  }
};

// Symbol.toStringTag
class MyClass {
  get [Symbol.toStringTag]() {
    return 'MyClass';
  }
}

console.log(Object.prototype.toString.call(new MyClass())); 
// [object MyClass]
```

### 13. Maps va Sets

```javascript
// Map - kalit-qiymat juftliklari (har qanday tip kalit bo'lishi mumkin)
const map = new Map();

map.set('name', 'John');
map.set(42, 'number key');
map.set({id: 1}, 'object key');

console.log(map.get('name')); // John
console.log(map.size); // 3
console.log(map.has('name')); // true

map.delete('name');
map.clear();

// Iteration
for (const [key, value] of map) {
  console.log(key, value);
}

// Set - unique qiymatlar to'plami
const set = new Set();

set.add(1);
set.add(2);
set.add(2); // Duplicate - ignore qilinadi
set.add(3);

console.log(set.size); // 3
console.log(set.has(2)); // true

set.delete(2);
set.clear();

// Array dan duplicatelarni olib tashlash
const numbers = [1, 2, 2, 3, 4, 4, 5];
const unique = [...new Set(numbers)]; // [1, 2, 3, 4, 5]

// WeakMap va WeakSet - garbage collection uchun
const wm = new WeakMap();
let obj = {};
wm.set(obj, 'value');
obj = null; // WeakMap avtomatik tozalanadi
```

---

## ES2016 (ES7)

### 1. Array.prototype.includes

```javascript
// Old way
const numbers = [1, 2, 3, 4, 5];
console.log(numbers.indexOf(3) !== -1); // true

// New way
console.log(numbers.includes(3)); // true
console.log(numbers.includes(10)); // false

// NaN bilan ishlaydi
console.log([1, 2, NaN].includes(NaN)); // true
```

### 2. Exponentiation Operator (**)

```javascript
// Old way
console.log(Math.pow(2, 3)); // 8

// New way
console.log(2 ** 3); // 8
console.log(10 ** -1); // 0.1

let x = 2;
x **= 3; // x = x ** 3
console.log(x); // 8
```

---

## ES2017 (ES8)

### 1. Async/Await

```javascript
// Promise bilan
function getUser() {
  return fetch('/api/user')
    .then(response => response.json())
    .then(user => {
      return fetch(`/api/posts/${user.id}`);
    })
    .then(response => response.json())
    .then(posts => {
      console.log(posts);
    })
    .catch(error => console.error(error));
}

// Async/Await bilan
async function getUser() {
  try {
    const response = await fetch('/api/user');
    const user = await response.json();
    
    const postsResponse = await fetch(`/api/posts/${user.id}`);
    const posts = await postsResponse.json();
    
    console.log(posts);
  } catch (error) {
    console.error(error);
  }
}

// Parallel execution
async function getData() {
  const [users, posts, comments] = await Promise.all([
    fetch('/api/users').then(r => r.json()),
    fetch('/api/posts').then(r => r.json()),
    fetch('/api/comments').then(r => r.json())
  ]);
  
  return { users, posts, comments };
}

// Top-level await (ES2022)
// module ichida faqat
const data = await fetch('/api/data').then(r => r.json());
```

### 2. Object.entries() va Object.values()

```javascript
const person = {
  name: "John",
  age: 25,
  city: "New York"
};

// Object.entries
console.log(Object.entries(person));
// [["name", "John"], ["age", 25], ["city", "New York"]]

// Object aylantirish
const entries = Object.entries(person);
const newObj = Object.fromEntries(entries);

// Object.values
console.log(Object.values(person));
// ["John", 25, "New York"]

// Iteration
for (const [key, value] of Object.entries(person)) {
  console.log(`${key}: ${value}`);
}
```

### 3. String padding

```javascript
// padStart va padEnd
const str = "5";
console.log(str.padStart(3, "0")); // "005"
console.log(str.padEnd(3, "0")); // "500"

// Credit card formatting
const cardNumber = "1234567812345678";
const formatted = cardNumber.match(/.{1,4}/g).join(' ');
console.log(formatted); // "1234 5678 1234 5678"

// Time formatting
const hours = "9";
const minutes = "5";
console.log(`${hours.padStart(2, "0")}:${minutes.padStart(2, "0")}`);
// "09:05"
```

### 4. Object.getOwnPropertyDescriptors()

```javascript
const obj = {
  name: "John",
  get fullName() {
    return this.name + " Doe";
  }
};

const descriptors = Object.getOwnPropertyDescriptors(obj);
console.log(descriptors);

// Clone with getters/setters
const clone = Object.create(
  Object.getPrototypeOf(obj),
  Object.getOwnPropertyDescriptors(obj)
);
```

### 5. Trailing commas in functions

```javascript
// Function parameters va arguments da trailing comma
function myFunction(
  param1,
  param2,
  param3, // trailing comma - OK
) {
  // ...
}

myFunction(
  arg1,
  arg2,
  arg3, // trailing comma - OK
);
```

---

## ES2018 (ES9)

### 1. Rest/Spread for Objects

```javascript
// Rest properties
const person = {
  name: "John",
  age: 25,
  city: "New York",
  country: "USA"
};

const { name, age, ...address } = person;
console.log(address); // { city: "New York", country: "USA" }

// Spread properties
const defaults = { theme: "light", fontSize: 14 };
const userPrefs = { fontSize: 16, language: "uz" };
const config = { ...defaults, ...userPrefs };
// { theme: "light", fontSize: 16, language: "uz" }

// Shallow clone
const clone = { ...person };

// Merge objects
const merged = { ...obj1, ...obj2, ...obj3 };
```

### 2. Asynchronous Iteration

```javascript
// Async generators
async function* asyncGenerator() {
  yield await Promise.resolve(1);
  yield await Promise.resolve(2);
  yield await Promise.resolve(3);
}

// For-await-of
async function processData() {
  for await (const value of asyncGenerator()) {
    console.log(value);
  }
}

// Real world example
async function* fetchPages(url) {
  let page = 1;
  while (true) {
    const response = await fetch(`${url}?page=${page}`);
    const data = await response.json();
    if (data.length === 0) break;
    yield data;
    page++;
  }
}

for await (const pageData of fetchPages('/api/items')) {
  console.log(pageData);
}
```

### 3. Promise.finally()

```javascript
fetch('/api/data')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error(error))
  .finally(() => {
    // Har doim ishga tushadi
    console.log('Request completed');
    hideLoadingSpinner();
  });

// Async/await bilan
async function getData() {
  try {
    const data = await fetch('/api/data');
    console.log(data);
  } catch (error) {
    console.error(error);
  } finally {
    hideLoadingSpinner();
  }
}
```

### 4. RegExp improvements

```javascript
// Named capture groups
const datePattern = /(?<year>\d{4})-(?<month>\d{2})-(?<day>\d{2})/;
const match = datePattern.exec('2024-01-15');
console.log(match.groups.year); // "2024"
console.log(match.groups.month); // "01"
console.log(match.groups.day); // "15"

// Lookbehind assertions
const pattern = /(?<=\$)\d+/;
console.log('$100'.match(pattern)); // ["100"]

// Unicode property escapes
const pattern = /\p{Script=Greek}/u;
console.log(pattern.test('π')); // true

// s (dotAll) flag
console.log(/hello.world/.test('hello\nworld')); // false
console.log(/hello.world/s.test('hello\nworld')); // true
```

---

## ES2019 (ES10)

### 1. Array.flat() va Array.flatMap()

```javascript
// Array.flat()
const nested = [1, [2, 3], [4, [5, 6]]];
console.log(nested.flat()); // [1, 2, 3, 4, [5, 6]]
console.log(nested.flat(2)); // [1, 2, 3, 4, 5, 6]
console.log(nested.flat(Infinity)); // To'liq flatten

// Array.flatMap()
const numbers = [1, 2, 3];
console.log(numbers.flatMap(x => [x, x * 2]));
// [1, 2, 2, 4, 3, 6]

// flatMap = map + flat(1)
const sentences = ["Hello world", "How are you"];
console.log(sentences.flatMap(s => s.split(' ')));
// ["Hello", "world", "How", "are", "you"]
```

### 2. Object.fromEntries()

```javascript
// Array dan object yaratish
const entries = [
  ['name', 'John'],
  ['age', 25]
];
const obj = Object.fromEntries(entries);
console.log(obj); // { name: "John", age: 25 }

// Map dan object
const map = new Map([
  ['name', 'John'],
  ['age', 25]
]);
const obj = Object.fromEntries(map);

// Object transform qilish
const prices = {
  apple: 100,
  banana: 50,
  orange: 75
};

const discounted = Object.fromEntries(
  Object.entries(prices).map(([key, value]) => [key, value * 0.9])
);

// URL params
const params = new URLSearchParams('name=John&age=25');
const obj = Object.fromEntries(params);
```

### 3. String.trimStart() va String.trimEnd()

```javascript
const str = "   Hello World   ";

console.log(str.trimStart()); // "Hello World   "
console.log(str.trimEnd()); // "   Hello World"
console.log(str.trim()); // "Hello World"

// Aliases
console.log(str.trimLeft()); // Same as trimStart()
console.log(str.trimRight()); // Same as trimEnd()
```

### 4. Optional catch binding

```javascript
// Old way
try {
  JSON.parse(data);
} catch (error) {
  console.log('Invalid JSON');
}

// New way - error o'zgaruvchisi shart emas
try {
  JSON.parse(data);
} catch {
  console.log('Invalid JSON');
}
```

### 5. Symbol.description

```javascript
const sym = Symbol('My symbol description');

// Old way
console.log(sym.toString()); // "Symbol(My symbol description)"

// New way
console.log(sym.description); // "My symbol description"
```

---

## ES2020 (ES11)

### 1. Optional Chaining (?.)

```javascript
// Old way
const city = user && user.address && user.address.city;

// New way
const city = user?.address?.city;

// Array elements
const firstPost = user?.posts?.[0];

// Function calls
const result = obj?.someMethod?.();

// Real world example
function getUserCity(user) {
  return user?.address?.city ?? 'Unknown';
}

// Combining with arrays
const users = [
  { name: 'John', address: { city: 'NYC' } },
  { name: 'Jane' },
  null
];

users.forEach(user => {
  console.log(user?.address?.city); // NYC, undefined, undefined
});
```

### 2. Nullish Coalescing (??)

```javascript
// || operatori false values bilan muammo
const value1 = 0 || 'default'; // 'default'
const value2 = '' || 'default'; // 'default'
const value3 = false || 'default'; // 'default'

// ?? faqat null va undefined uchun
const value1 = 0 ?? 'default'; // 0
const value2 = '' ?? 'default'; // ''
const value3 = false ?? 'default'; // false
const value4 = null ?? 'default'; // 'default'
const value5 = undefined ?? 'default'; // 'default'

// Real world example
function createUser(options) {
  return {
    name: options.name ?? 'Guest',
    age: options.age ?? 0,
    theme: options.theme ?? 'light'
  };
}

// Optional chaining bilan
const port = config?.server?.port ?? 3000;
```

### 3. BigInt

```javascript
// Old way - Number.MAX_SAFE_INTEGER cheklovi
console.log(Number.MAX_SAFE_INTEGER); // 9007199254740991
console.log(9007199254740991 + 1); // 9007199254740992
console.log(9007199254740991 + 2); // 9007199254740992 - XATO!


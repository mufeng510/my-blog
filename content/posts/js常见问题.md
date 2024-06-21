---
title: js常见问题
tags: [面试题]
date: 2024-06-07 14:32:20
draft: true
hideInList: false
isTop: false
feature: 
---
[TOC]

## es的新特性

ES（ECMAScript）是JavaScript的标准，随着每年的更新，它不断引入新的特性来提高语言的功能性和开发者的生产力。以下是一些近年来ES的主要新特性：

### ES6（ECMAScript 2015）
1. **let 和 const**：用于声明变量，具有块级作用域。
2. **箭头函数**：简化函数表达式，并且不绑定 `this`。
   ```javascript
   const add = (a, b) => a + b;
   ```
3. **模板字符串**：使用反引号（\` \`）创建多行字符串和内嵌表达式。
   ```javascript
   const name = "World";
   const greeting = `Hello, ${name}!`;
   ```
4. **解构赋值**：从数组或对象中提取数据并赋值给变量。
   ```javascript
   const [a, b] = [1, 2];
   const {name, age} = {name: 'John', age: 30};
   ```
5. **默认参数**：函数参数的默认值。
   ```javascript
   function multiply(a, b = 1) {
       return a * b;
   }
   ```
6. **类（Class）**：更清晰、更简单的面向对象编程方式。
   ```javascript
   class Person {
       constructor(name) {
           this.name = name;
       }
       greet() {
           console.log(`Hello, ${this.name}`);
       }
   }
   ```
7. **模块（Modules）**：模块化导入和导出。
   ```javascript
   // 导出
   export const name = 'John';
   // 导入
   import {name} from './module';
   ```

### ES7（ECMAScript 2016）
1. **指数操作符**：`**` 代替 `Math.pow`。
   ```javascript
   const squared = 2 ** 3; // 8
   ```
2. **Array.prototype.includes**：判断数组是否包含某个值。
   ```javascript
   const arr = [1, 2, 3];
   console.log(arr.includes(2)); // true
   ```

### ES8（ECMAScript 2017）
1. **Async/Await**：简化异步代码的编写。
   ```javascript
   async function fetchData() {
       const response = await fetch('url');
       const data = await response.json();
       return data;
   }
   ```
2. **Object.entries() 和 Object.values()**：获取对象的键值对或值。
   ```javascript
   const obj = {a: 1, b: 2};
   console.log(Object.entries(obj)); // [['a', 1], ['b', 2]]
   console.log(Object.values(obj));  // [1, 2]
   ```

### ES9（ECMAScript 2018）
1. **Rest/Spread 属性**：用于对象。
   ```javascript
   const {a, ...rest} = {a: 1, b: 2, c: 3};
   console.log(rest); // {b: 2, c: 3}
   ```
2. **Promise.finally()**：在 Promise 执行完之后，无论成功或失败，都会执行的回调函数。
   ```javascript
   fetch('url')
       .then(response => response.json())
       .catch(error => console.error(error))
       .finally(() => console.log('Finished'));
   ```

### ES10（ECMAScript 2019）
1. **Array.prototype.flat() 和 flatMap()**：用于数组的扁平化和映射。
   ```javascript
   const arr = [1, [2, [3, 4]]];
   console.log(arr.flat(2)); // [1, 2, 3, 4]
   ```
2. **Object.fromEntries()**：将键值对数组转换为对象。
   ```javascript
   const entries = [['a', 1], ['b', 2]];
   const obj = Object.fromEntries(entries); // {a: 1, b: 2}
   ```

### ES11（ECMAScript 2020）
1. **Optional Chaining (?.)**：简化多层对象属性的安全访问。
   ```javascript
   const user = {};
   console.log(user?.profile?.name); // undefined
   ```
2. **Nullish Coalescing Operator (??)**：提供默认值。
   ```javascript
   const foo = null ?? 'default string'; // 'default string'
   ```



## var、let、const的区别和作用域
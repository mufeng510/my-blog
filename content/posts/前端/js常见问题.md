---
title: js常见问题
tags:
  - 面试题
date: 2024-06-07 14:32:20
draft: false
hideInList: false
isTop: false
feature:
---

## es的新特性

ES（ECMAScript）是JavaScript的标准，随着每年的更新，它不断引入新的特性来提高语言的功能性和开发者的生产力。以下是一些近年来ES的主要新特性：

### ES6（ECMAScript 2015）
1. **let 和 const**：用于声明变量，具有块级作用域。
2. **箭头函数**：简化函数表达式，并且不绑定 `this`。
3. **模板字符串**：使用反引号（\` \`）创建多行字符串和内嵌表达式。
4. **解构赋值**：从数组或对象中提取数据并赋值给变量。
	```javascript
	   const [a, b] = [1, 2];
	   const {name, age} = {name: 'John', age: 30};
   ```
1. **默认参数**：函数参数的默认值。
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

在JavaScript中，`var`、`let` 和 `const` 是用于声明变量的关键字，它们之间的区别主要体现在作用域、提升（hoisting）以及是否可以重新赋值上。下面详细解释它们的区别：

1. `var`
- **作用域**：`var` 声明的变量具有函数作用域或全局作用域。它不具有块级作用域。
  ```javascript
  function example() {
      if (true) {
          var x = 5;
      }
      console.log(x); // 5，因为 var 没有块级作用域
  }
  ```
- **提升**：`var` 声明的变量会被提升到函数或全局作用域的顶部，但初始化不会提升。
  ```javascript
  console.log(a); // undefined
  var a = 5;
  // 等同于
  var a;
  console.log(a); // undefined
  a = 5;
  ```
- **重新赋值**：可以重新赋值和重新声明。
  ```javascript
  var b = 1;
  var b = 2; // 合法
  b = 3; // 合法
  ```

 2. `let`
- **作用域**：`let` 声明的变量具有块级作用域。
  ```javascript
  function example() {
      if (true) {
          let y = 5;
          console.log(y); // 5
      }
      console.log(y); // ReferenceError: y is not defined，因为 y 只在 if 块内可见
  }
  ```
- **提升**：`let` 声明的变量会提升到块的顶部，但在声明之前不能访问（暂时性死区）。
  ```javascript
  console.log(z); // ReferenceError: Cannot access 'z' before initialization
  let z = 5;
  ```
- **重新赋值**：可以重新赋值，但不能重新声明。
  ```javascript
  let c = 1;
  // let c = 2; // SyntaxError: Identifier 'c' has already been declared
  c = 3; // 合法
  ```

3. `const`
- **作用域**：`const` 声明的变量具有块级作用域。
  ```javascript
  function example() {
      if (true) {
          const w = 5;
          console.log(w); // 5
      }
      console.log(w); // ReferenceError: w is not defined，因为 w 只在 if 块内可见
  }
  ```
- **提升**：`const` 声明的变量会提升到块的顶部，但在声明之前不能访问（暂时性死区）。
  ```javascript
  console.log(v); // ReferenceError: Cannot access 'v' before initialization
  const v = 5;
  ```
- **重新赋值**：不能重新赋值或重新声明。声明时必须初始化。
  ```javascript
  const d = 1;
  // const d = 2; // SyntaxError: Identifier 'd' has already been declared
  // d = 3; // TypeError: Assignment to constant variable
  ```

总结
- **作用域**：`var` 有函数作用域或全局作用域；`let` 和 `const` 有块级作用域。
- **提升**：`var` 声明会提升到作用域顶部；`let` 和 `const` 也会提升但存在暂时性死区。
- **重新赋值和重新声明**：`var` 可以重新赋值和重新声明；`let` 可以重新赋值但不能重新声明；`const` 既不能重新赋值也不能重新声明，声明时必须初始化。

这些区别使得 `let` 和 `const` 在大多数情况下更适合用于现代 JavaScript 编程，因为它们可以帮助避免变量提升带来的意外行为，并且块级作用域也提高了代码的可读性和可维护性。

## 原型和原型链

 原型（Prototype）

1. **构造函数与原型对象**：
    
    - 在JavaScript中，函数也是对象，每个函数都有一个特殊的属性称为原型（prototype）。
    - 当我们创建一个函数时，JavaScript会为该函数自动添加一个prototype属性，指向一个对象，这个对象就是该函数的原型对象。
2. **原型对象的作用**：
    
    - 原型对象包含可供其他对象继承的属性和方法。
    - 当我们创建一个新对象（实例）时，这个对象会从其构造函数的原型对象上继承属性和方法。

 原型链（Prototype Chain）

1. **定义**：
    
    - 每个对象都有一个原型对象，而原型对象也有自己的原型，如果该原型还有原型，则形成了所谓的原型链。
    - 当试图访问一个对象的属性或方法时，JavaScript引擎会首先在当前对象上查找，如果找不到，则会沿着原型链依次向上查找，直到找到对应的属性或方法或者达到原型链的末端（null）。
2. **原型链的终点**：
    
    - 所有对象的原型链的顶端是Object.prototype，它是JavaScript中所有对象的基础，包含一些基本的方法，例如toString()和valueOf()。

## 事件循环

事件循环（Event Loop）是JavaScript运行时的一个重要机制，用于处理异步操作。它允许JavaScript执行非阻塞代码，使其能够处理I/O操作、计时器等异步任务，而不必等待这些操作完成。以下是事件循环的工作原理简要说明：

1. **执行栈（Call Stack）**：当JavaScript代码执行时，函数调用会被压入执行栈中，执行完毕后出栈。如果执行栈为空，事件循环就会检查事件队列。
    
2. **事件队列（Event Queue）**：当异步操作完成时，例如定时器到期、I/O操作完成或Promise状态变更，相应的回调函数会被添加到事件队列中。
    
3. **事件循环（Event Loop）**：事件循环会不断检查执行栈是否为空，如果为空且事件队列中有待处理的回调函数，就会将回调函数从事件队列中移到执行栈中并执行。
    
4. **宏任务（Macro-tasks）与微任务（Micro-tasks）**：事件循环还区分宏任务（例如setTimeout、setInterval）和微任务（例如Promise的then、catch）。在每个宏任务执行完后，事件循环会先执行所有的微任务，然后再开始下一个宏任务。

## this指向

- 默认绑定
	当函数独立调用时，this默认绑定window
- 隐式绑定
	调用的对象内部有对函数的引用
- 显式绑定
	不希望在对象内部包含这个函数的引用，但又希望通过对象强制调用，使用call/apply/bind进行显式绑定
- new绑定
	通过new关键字来创建构造函数的实例，绑定this

## for in 和 for of 有什么不同

for...in 循环
功能：用于遍历对象的可枚举属性。
遍历内容：包括对象、数组的所有可枚举属性，包括原型链上的键。

for...of 循环
功能：遍历拥有迭代器对象的集合，如数组、字符串、Map、Set等。
限制：不能遍历普通对象。
特点：与 forEach() 不同，for...of 可以正确响应 break、continue 和 return 语句。

使用建议
遍历数组：使用 for...of。
遍历对象：使用 for...in。

## 闭包及其应用场景

闭包（Closure）是指函数和声明该函数的词法环境的组合。具体来说，闭包允许函数访问定义时的词法作用域（即它被创建时所处的环境），而不是调用时的作用域。这种机制使得函数可以保留对其词法作用域外部变量的引用，即使函数是在其词法作用域之外调用。

1. 单例模式
2. 函数防抖
3. 私有变量
4. 避免内存销毁


## Promise

`Promise` 是 JavaScript 中用于处理异步操作的对象。它代表一个未来可能完成或失败的操作及其结果值。`Promise` 提供了一种更优雅和方便的方式来处理异步操作，避免了传统的回调地狱。

基本概念

1. **状态**：Promise 有三种状态：
    
    - **pending**（进行中）：初始状态，既不是成功也不是失败状态。
    - **fulfilled**（已成功）：操作成功完成。
    - **rejected**（已失败）：操作失败。
2. **值**：Promise 具有一个值，该值在状态从 pending 变为 fulfilled 时变为最终值，或在状态从 pending 变为 rejected 时变为拒绝的原因。

Promise 的常用方法有 `.then()`, `.catch()`, 和 `.finally()`。

**Promise.all**：用于处理多个 Promise，所有 Promise 都成功时返回一个包含所有结果的数组，如果有一个 Promise 失败，则返回失败的原因。

**Promise.race**：用于处理多个 Promise，只要有一个 Promise 成功或失败，就返回这个 Promise 的结果。

# call、apply、bind三者的用法和区别

call、apply都是调用函数，区别在于传参方式，call是分别传递，apply是将参数作为一个数组传入

bind是创建了一个新函数，传参与call相同

# js的数据类型

值类型(基本类型)：字符串（String）、数字(Number)、布尔(Boolean)、空（Null）、未定义（Undefined）、Symbol。

引用数据类型（对象类型）：对象(Object)、数组(Array)、函数(Function)，还有两个特殊的对象：正则（RegExp）和日期（Date）。

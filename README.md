# ES6-skills
先看一下 ES6 的新特性：
- Default Parameters in ES6（默认参数）
- Template Literals in ES6（模板文本）
- Multi-line Strings in ES6（多行字符串）
- Destructuring Assignment in ES6（解构赋值）
- Enhanced Object Literals in ES6（增强的对象文本）
- Arrow Functions in ES6（箭头函数）
- Promises in ES6
- Block-Scoped Constructs Let and Const（块作用域构造 Let and Const）
- Classes in ES6（类）
- Modules in ES6（模块）
### Hack #1: Swap variables 交换变量
使用 Array Destructuring 交换值
```
let a = 'world', b = 'hello'
[a, b] = [b, a]
console.log(a) // -> hello
console.log(b) // -> world
// Yes, it's magic
```
### Hack #2 : Async/Await with Destructuring
下面这段代码可以同时发起两个异步请求，把请求结果分别附到 user 和 account 中
```
const [user, account] = await Promise.all([
  fetch('/user'),
  fetch('/account')
])
```
### Hack #3 :  Debugging
```
const a = 5, b = 6, c = 7
console.log({ a, b, c })
// outputs this nice object:
// {
//    a: 5,
//    b: 6,
//    c: 7
// }
```
### Hack #4 : One liners
更紧凑的数组操作语法
```
// Find max value
const max = (arr) => Math.max(...arr);
max([123, 321, 32]) // outputs: 321
// Sum array
const sum = (arr) => arr.reduce((a, b) => (a + b), 0)
sum([1, 2, 3, 4]) // output: 10
```
### Hack #5 :  Array concatenation
展开运算符可以用来代替 concat
```
const one = ['a', 'b', 'c']
const two = ['d', 'e', 'f']
const three = ['g', 'h', 'i']
// Old way #1
const result = one.concat(two, three)
// Old way #2
const result = [].concat(one, two, three)
// New
const result = [...one, ...two, ...three]
```
### Hack #6 : Cloning
```
const obj = { ...oldObj }
const arr = [ ...oldArr ]
```
### Hack #7 : Named parameters 参数命名
```
const getStuffNotBad = (id, force, verbose) => {
  ...do stuff
}
const getStuffAwesome = ({ id, name, force, verbose }) => {
  ...do stuff
}
// Somewhere else in the codebase... WTF is true, true?
getStuffNotBad(150, true, true)
// Somewhere else in the codebase... I ❤ JS!!!
getStuffAwesome({ id: 150, force: true, verbose: true })
```

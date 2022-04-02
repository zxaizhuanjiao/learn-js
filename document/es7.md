## ES2016(ES7)  
1、Array.prototype.includes()   
includes() 方法用来判断一个数组是否包含一个指定的值，如果包含则返回 true，否则返回 false   
语法：arr.includes(valueToFind[, fromIndex])   
valueToFind：需要查找的元素值   
fromIndex：可选 从fromIndex 索引处开始查找 valueToFind。如果为负值（即从末尾开始往前跳 fromIndex 的绝对值个索引，然后往后搜寻）。默认为 0   
eg：const arr = ['es6', 'es7', 'es8'];console.log(arr.includes('es7')) // true;   
注意：使用 includes()查找字符串是区分大小写的   
但是使用 includes()只能判断简单类型的数据，对于复杂类型的数据，比如对象类型的数组，二维数组，这些是无法判断的。  
const arr = ['es6', ['es7', 'es8'], 'es9',{name:"jimmy"}]   
console.log(arr.includes(["es7", "es8"])); // false   
console.log(arr.includes({name:"jimmy"})); // false   
能识别NaN，indexOf是不能识别NaN的   
const arr = ['es6', 'es7', NaN, 'es8']console.log(arr.includes(NaN)) // trueconsole.log(arr.indexOf(NaN)) // -1复制代码   
最后，如果只想知道某个值是否在数组中存在，而并不关心它的索引位置，建议使用includes(),如果想获取一个值在数组中的位置，那么使用indexOf方法。   

2、幂运算符**   
console.log(2 ** 10); // 1024  
其他写法：   
function pow(x, y) {
    let result = 1
    for (let i = 0; i < y; i++) {
        result *= x
    }
    return result
}   
console.log(Math.pow(2, 10)); // 1024   

## ES2017(ES8)
1、Object.values()    
Object.values 方法返回一个数组，成员是参数对象自身的（不含继承的）所有可遍历（enumerable）属性的键值   
eg: const obj = {  name: "jimmy",  age: 18,  height: 188};    
    console.log(Object.values(obj));    
    结果：[ 'jimmy', 18, 188 ]   
2、Object.entries()    
Object.entries() 方法返回一个数组，成员是参数对象自身的（不含继承的）所有可遍历属性的键值对数组   
eg：const obj = {  name: "jimmy",  age: 18,  height: 188};   
    console.log(Object.entries(obj)); // [ [ 'name', 'jimmy' ], [ 'age', 18 ], [ 'height', 188 ] ]   
    console.log(Object.entries([1, 2, 3])); // [ [ '0', 1 ], [ '1', 2 ], [ '2', 3 ] ]   
3、Object.getOwnPropertyDescriptors()   
Object.getOwnPropertyDescriptors() 方法用来获取一个对象的所有自身属性的描述符   
eg：const obj = {  name: "jimmy",  age: 18,  height: 188};   
    const desc = Object.getOwnPropertyDescriptors(obj);   
    console.log(desc);   
    // 打印结果
    {
        name: {
            value: 'jimmy',
            writable: true,
            enumerable: true,
            configurable: true
        },
        age: { 
            value: 18, 
            writable: true,
            enumerable: true, 
            configurable: true 
        }
    }    
上面打印结果中的 value表示当前对象的默认值;writable表示对象属性是否可以修改;enumerable表示当前这个属性是否可以出现在对象的枚举属性中;configurable表示当前对象的属性能否用delete删除;   
那这些对象的属性我们怎么设置和修改他们呢，我们可以使用es5的 Object.defineProperty()   
const obj = {};
Object.defineProperty(obj, "name", {
  value: "jimmy",
  writable: true,
  configurable: true,
  enumerable: true,
});
Object.defineProperty(obj, "age", {
  value: 34,
  writable: true,
  configurable: true,
  enumerable: true,
});
console.log(obj); // { name: 'jimmy', age: 34 }   
4、String.prototype.padStart   
语法：str.padStart(targetLength [, padString])   
targetLength：当前字符串需要填充到的目标长度。如果这个数值小于当前字符串的长度，则返回当前字符串本身   
padString（可选）：填充字符串。如果字符串太长，使填充后的字符串长度超过了目标长度，则只保留最左侧的部分，其他部分会被截断。此参数的默认值为 " "   
eg：'abc'.padStart(10);         // "       abc"
    'abc'.padStart(10, "foo");  // "foofoofabc"
    'abc'.padStart(6,"123465"); // "123abc"
    'abc'.padStart(8, "0");     // "00000abc"
    'abc'.padStart(1);          // "abc"    
5、String.prototype.padEnd  
把指定字符串填充到字符串尾部，返回新字符串   
'abc'.padEnd(10, "foo");   // "abcfoofoof"   
'abc'.padEnd(1);           // "abc"   
'abc'.padEnd(10);          // "abc       "   
6、async/await（是 JavaScript 异步编程的一个重大改进，提供了在不阻塞主线程的情况下使用同步代码实现异步访问资源的能力，并且使得代码逻辑更加清晰）  

## ES2018（ES9）   
1、Object Rest & Spread   
（1）spread语法：
    const input = {  a: 1,  b: 2,  c: 3,}   
    const output = {  ...input,  c: 4}   
    console.log(output) // {a: 1, b: 2, c: 4}   
（2）Object rest语法：    
    const input = {  a: 1,  b: 2,  c: 3}   
    let { a, ...rest } = input   
    console.log(a, rest) // 1 {b: 2, c: 3}   

2、for await of   
异步迭代器(for-await-of)：循环等待每个Promise对象变为resolved状态才进入下一步   
for...of 是同步运行的   
function TimeOut(time){
    return new Promise(function(resolve, reject) {
        setTimeout(function() {
            resolve(time)
        }, time)
    })
}    
async function test() {
    let arr = [TimeOut(2000), TimeOut(1000), TimeOut(3000)]
    for (let item of arr) {  
     console.log(Date.now(),item.then(console.log))
    }
}   
test()  
即for of 方法不能遍历异步迭代器，得到的结果并不是我们所期待的，于是 for await of 就粉墨登场啦   
function TimeOut(time) {
    return new Promise(function(resolve, reject) {
        setTimeout(function() {
            resolve(time)
        }, time)
    })
}   
async function test() {
    let arr = [TimeOut(2000), TimeOut(1000), TimeOut(3000)]
    for await (let item of arr) {
        console.log(Date.now(), item)
    }
}   
test()   
// 1560092345730 2000   
// 1560092345730 1000   
// 1560092346336 3000   

3、Promise.prototype.finally()   
Promise.prototype.finally() 方法返回一个Promise，在promise执行结束时，无论结果是fulfilled或者是rejected，在执行then()和catch()后，都会执行finally指定的回调函数。这为指定执行完promise后，无论结果是fulfilled还是rejected都需要执行的代码提供了一种方式，避免同样的语句需要在then()和catch()中各写一次的情况   
new Promise((resolve, reject) => {
    setTimeout(() => {
        resolve('success')
        // reject('fail')
    }, 1000)
}).then(res => {
    console.log(res)
}).catch(err => {
    console.log(err)
}).finally(() => {
    console.log('finally')
})   

4、String 扩展   
const foo = (a, b, c) => {
    console.log(a)
    console.log(b)
    console.log(c)
}
const name = 'jimmy'
const age = 18
foo `这是${name},他的年龄是${age}岁`  

## ES2019（ES10）  
1、Object.fromEntries()   
方法 Object.fromEntries() 把键值对列表转换为一个对象，这个方法是和 Object.entries() 相对的   
eg：Object.fromEntries([    ['foo', 1],    ['bar', 2]])// {foo: 1, bar: 2}   
案例1：Object 转换操作   
const obj = {name: 'jimmy',age: 18}   
const entries = Object.entries(obj);console.log(entries);// [Array(2), Array(2)]   
// ES10   
const fromEntries = Object.fromEntries(entries);console.log(fromEntries);// {name: "jimmy", age: 18}   
案例2：Map 转 Object    
const map = new Map();map.set('name', 'jimmy');map.set('age', 18);console.log(map) // {'name' => 'jimmy', 'age' => 18}   
const obj = Object.fromEntries(map);console.log(obj);// {name: "jimmy", age: 18}    
案例3：过滤    
course表示所有课程，想请求课程分数大于80的课程组成的对象：    
const course = {math: 80,english: 85,chinese: 90};  
const res = Object.entries(course).filter(([key, val]) => val > 80);   
console.log(res) // [ [ 'english', 85 ], [ 'chinese', 90 ] ]   
console.log(Object.fromEntries(res)) // { english: 85, chinese: 90 }   
案例4：url的search参数转换   
const queryString = "?name=jimmy&age=18&height=1.88";   
const queryParams = new URLSearchParams(queryString);    
const paramObj = Object.fromEntries(queryParams);    
console.log(paramObj); // { name: 'jimmy', age: '18', height: '1.88' }   

2、Array.prototype.flat()   
语法：let newArray = arr.flat([depth])   
depth 可选；指定要提取嵌套数组的结构深度，默认值为 1    
flat() 方法会按照一个可指定的深度递归遍历数组，并将所有元素与遍历到的子数组中的元素合并为一个新数组返回    
const arr1 = [0, 1, 2, [3, 4]];   
console.log(arr1.flat());  //  [0, 1, 2, 3, 4]   
const arr2 = [0, 1, 2, [[[3, 4]]]];   
console.log(arr2.flat(2));  //  [0, 1, 2, [3, 4]]   
//使用 Infinity，可展开任意深度的嵌套数组   
var arr4 = [1, 2, [3, 4, [5, 6, [7, 8, [9, 10]]]]];   
arr4.flat(Infinity); // [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]   
   
// `flat()` 方法会移除数组中的空项:   
var arr5 = [1, 2, , 4, 5];   
arr5.flat(); // [1, 2, 4, 5]

[原文链接](https://www.jianshu.com/p/dedb5a94e67f)






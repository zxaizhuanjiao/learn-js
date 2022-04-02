# learn-js

## ES7-ES12
[es7以上](document/es7.md)

### JS简介  
1、JavaScript 能够改变 HTML 内容  
document.getElementById('xxx').innerHTML = 'xxxxxx'   
2、JavaScript 能够改变 HTML 属性   
document.getElementById('xxx').src = 'xxxxxx'  
3、JavaScript 能够改变 HTML 样式 (CSS)   
document.getElementById("demo").style.fontSize = "25px";  
4、JavaScript 能够隐藏 HTML 元素   
document.getElementById("demo").style.display="none";  

### JS变量   
1、JavaScript 标识符   
所有 JavaScript 变量必须以唯一的名称的标识。这些唯一的名称称为标识符。   
标识符可以是短名称（比如 x 和 y），或者更具描述性的名称（age、sum、totalVolume）。  
构造变量名称（唯一标识符）的通用规则是：  
名称可包含字母、数字、下划线和美元符号  
名称必须以字母开头   
名称也可以 $ 和 _ 开头（但是在本教程中我们不会这么做）  
名称对大小写敏感（y 和 Y 是不同的变量）  
保留字（比如 JavaScript 的关键词）无法用作变量名称  
提示：JavaScript 标识符对大小写敏感。  

### JS let  
ES2015 引入了两个重要的 JavaScript 新关键词：let 和 const。   
这两个关键字在 JavaScript 中提供了块作用域（Block Scope）变量（和常量）。   
1、全局作用域  
全局（在函数之外）声明的变量拥有全局作用域。  
全局变量可以在 JavaScript 程序中的任何位置访问。  
2、函数作用域  
局部（函数内）声明的变量拥有函数作用域。   
局部变量只能在它们被声明的函数内访问。   
3、js块作用域   
通过 var 关键词声明的变量没有块作用域。在块 {} 内声明的变量可以从块之外进行访问。  
在 ES2015 之前，JavaScript 是没有块作用域的。可以使用 let 关键词声明拥有块作用域的变量。在块 {} 内声明的变量无法从块外访问：   
4、重新声明变量  
使用 var 关键字重新声明变量会带来问题。在块中重新声明变量也将重新声明块外的变量：   
var x = 10;
// 此处 x 为 10
{ 
  var x = 6;
  // 此处 x 为 6
}
// 此处 x 为 6   
使用 let 关键字重新声明变量可以解决这个问题。在块中重新声明变量不会重新声明块外的变量：  
var x = 10;
// 此处 x 为 10
{ 
  let x = 6;
  // 此处 x 为 6
}
// 此处 x 为 10  

### JS const  
ES2015 引入了两个重要的 JavaScript 新关键词：let 和 const。  
通过 const 定义的变量与 let 变量类似，但不能重新赋值：  
1、块作用域  
在块作用域内使用 const 声明的变量与 let 变量相似。  
2、在声明时赋值  
JavaScript const 变量必须在声明时赋值  
3、不是真正的常数   
它没有定义常量值。它定义了对值的常量引用。因此，我们不能更改常量原始值，但我们可以更改常量对象的属性。  
4、原始值  
如果我们将一个原始值赋给常量，我们就不能改变原始值  
5、常量对象可以更改  
您可以更改常量对象的属性：   
// 您可以创建 const 对象：
const car = {type:"porsche", model:"911", color:"Black"};
// 您可以更改属性：
car.color = "White";
// 您可以添加属性：
car.owner = "Bill";  
6、常量数组可以更改  
您可以更改常量数组的元素：  
// 您可以创建常量数组：
const cars = ["Audi", "BMW", "porsche"];
// 您可以更改元素：
cars[0] = "Honda";
// 您可以添加元素：
cars.push("Volvo");   
但是您无法重新为常量数组赋值：  
const cars = ["Audi", "BMW", "porsche"];
cars = ["Honda", "Toyota", "Volvo"];    // ERROR  
7、提升  
您可以在声明 var 变量之前就使用它：  
carName = "Volvo";    // 您可以在此处使用 carName
var carName;  
通过 const 定义的变量不会被提升到顶端。  
const 变量不能在声明之前使用：  
carName = "Volvo";    // 您不可以在此处使用 carName
const carName = "Volvo";  

### JS数据类型
Undefined 与 null 的值相等，但类型不相等   
undefined类型是undefined   
null类型是null  

### JS函数   

### JavaScript 对象   
1、JavaScript 对象   
对象也是变量。但是对象包含很多值。  
var car = {type:"porsche", model:"911", color:"white"};   
值以名称:值对的方式来书写（名称和值由冒号分隔）   
JavaScript 对象是被命名值的容器   
2、对象属性  
（JavaScript 对象中的）名称:值对被称为属性。  
var person = {firstName:"Bill", lastName:"Gates", age:62, eyeColor:"blue"};  
3、对象方法  
对象也可以有方法   
方法是在对象上执行的动作  
方法以函数定义被存储在属性中   
var person = {
  firstName: "Bill",
  lastName : "Gates",
  id       : 678,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};   
4、this关键词   
在函数定义中，this 引用该函数的“拥有者”  
在上面的例子中，this 指的是“拥有” fullName 函数的 person 对象；换言之，this.firstName 的意思是 this 对象的 firstName 属性  
5、对象定义   
6、访问对象属性   
objectName.propertyName 或者 objectName["propertyName"]   
7、访问对象方法  
objectName.methodName() 或者 name = person.fullName();   

### JavaScript 事件   
[事件](document/event.md)   

### JavaScript 字符串   
[字符串](document/string.md)   

### JavaScript 作用域
[作用域](document/zuoyongyu.md)   

### JavaScript this关键词   
[this](document/this.md)  

### JavaScript 箭头函数   
[箭头函数](document/jiantou.md)   

### JavaScript JSON   
[JSON](document/json.md)   

### JavaScript正则   
[正则](document/zhengze.md)   








## 循环
[循环](document/xunhuan.md)   
[object](document/object.md)
# react  
## jsx  
### jsx简介  
JSX（是react核心内容）是JavaScript XML的简写，表示在JavaScript代码中写XML（HTML）格式的代码   
优势：声明式语法更加直观、与HTML结构相同、提升开发效率  
### jsx使用  
1、使用JSX语法创建react元素：  
const title = <h1>hello,react</h1>  
使用ReactDOM.render()方法渲染react元素到页面中：  
ReactDOM.render(title, root)   
2、jsx注意点   
1）React元素的属性名使用驼峰命名法  
2）特殊属性名：class -> className、for -> htmlFor、tabindex -> tabIndex  
3）没有子节点的React元素可以用/>结束   
4）推荐：使用小括号包裹JSX，从而避免JS中的自动插入分号陷阱   
eg：使用小括号包裹JSX
const dv = (
    <div>Hello JSX</div>
)  
### JSX中使用JavaScript表达式   
1、嵌入JS表达式  
数据存储在JS中  
语法： { js表达式 }  






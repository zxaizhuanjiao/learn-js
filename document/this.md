var person = {
  firstName: "Bill",
  lastName : "Gates",
  id       : 678,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};   
### this是什么   
JavaScript this 关键词指的是它所属的对象   
它拥有不同的值，具体取决于它的使用位置：   
1）在方法中，this指的是所有者对象   
2）单独的情况下，this指的是全局对象   
3）在函数中，this指的是全局对象  
4）在函数中，严格模式下，this是undefined   
5）在事件中，this指的是接收事件的元素   
像 call() 和 apply() 这样的方法可以将 this 引用到任何对象   

### 方法中的this   
在对象方法中，this指的是此方法的“拥有者”  
在本页最上面的例子中，this指的是person对象   

### 单独的this   
在单独使用时，拥有者是全局对象，因此 this 指的是全局对象   
在浏览器窗口中，全局对象是 [object Window]：var x = this;   
在严格模式中，如果单独使用，那么 this 指的是全局对象 [object Window]：  
"use strict";
var x = this;   

### 函数中的 this（默认）   
在 JavaScript 函数中，函数的拥有者默认绑定 this，因此，在函数中，this 指的是全局对象 [object Window]   

### 函数中的 this（严格模式）   
JavaScript 严格模式不允许默认绑定   
因此，在函数中使用时，在严格模式下，this 是未定义的（undefined）   
"use strict";
function myFunction() {
  return this;
}   

### 事件处理程序中的 this   
在 HTML 事件处理程序中，this 指的是接收此事件的 HTML 元素：   
<button onclick="this.style.display='none'">
  点击来删除我！
</button>   

### 对象方法绑定   
在此例中，this 是 person 对象（person 对象是该函数的“拥有者”）：   
var person = {
  firstName  : "Bill",
  lastName   : "Gates",
  id         : 678,
  myFunction : function() {
    return this;
  }
};   

### 显式函数绑定   
call() 和 apply() 方法是预定义的 JavaScript 方法。它们都可以用于将另一个对象作为参数调用对象方法   


   



### JSON 是存储和传输数据的格式,JSON 经常在数据从服务器发送到网页时使用   

### JSON 语法规则   
1、数据是名称/值对   
2、数据由逗号分隔   
3、花括号保存对象  
4、方括号保存数组   

### JSON 数据 - 名称和值  
JSON 数据的书写方式是名称/值对，类似 JavaScript 对象属性    
名称/值对由（双引号中的）字段名构成，其后是冒号，再其后是值："firstName":"Bill"    
JSON 名称需要双引号。JavaScript 名称不需要   

### JSON 对象   
JSON 对象是在花括号内书写的，类似 JavaScript，对象能够包含多个名称/值对   
eg：{"firstName":"Bill", "lastName":"Gates"}   

### JSON 数组   
JSON 数组在方括号中书写，类似 JavaScript，数组能够包含对象   
eg："employees":[{"firstName":"Bill", "lastName":"Gates"}, {"firstName":"Steve", "lastName":"Jobs"}, {"firstName":"Alan", "lastName":"Turing"}]   

### 把 JSON 文本转换为 JavaScript 对象
JSON 的通常用法是从 web 服务器读取数据，然后在网页中显示数据   
为了简单起见，可以使用字符串作为输入演示   
1、创建包含 JSON 语法的 JavaScript 字符串   
var text = '{ "employees" : [' +'{ "firstName":"Bill" , "lastName":"Gates" },' +'{ "firstName":"Steve" , "lastName":"Jobs" },' +'{ "firstName":"Alan" , "lastName":"Turing" } ]}';   
2、使用 JavaScript 的内建函数 JSON.parse() 来把这个字符串转换为 JavaScript 对象   
var obj = JSON.parse(text);   

### 存储数据：JSON.stringify   

### 接收数据：JSON.parse   

[JSON教程](https://www.w3school.com.cn/js/js_json_intro.asp)



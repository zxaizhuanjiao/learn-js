## JavaScript 字符串   
JavaScript 字符串是引号中的零个或多个字符（单引号、双引号都可）  

### 字符串长度   
内建属性 length 可返回字符串的长度   

### 特殊字符  
反斜杠转义字符把特殊字符转换为字符串字符   
\' ====> '（单引号）   
\" ====> "（双引号）   
\\ ====> \（反斜杠）  
\b ====> 退格键   
\f ====> 换页   
\n ====> 换行   
\r ====> 回车   
\t ====> 水平制表符   
\v ====> 垂直制表符  
==：值相等   ===：类型和值都要相等   

## JavaScript 字符串方法   
### 字符串长度   
length 属性返回字符串的长度   

### 查找字符串中的字符串   
indexOf() 方法返回字符串中指定文本首次出现的索引（位置）   
lastIndexOf() 方法返回指定文本在字符串中最后一次出现的索引   
如果未找到文本， indexOf() 和 lastIndexOf() 均返回 -1   
两种方法都接受作为检索起始位置的第二个参数   
lastIndexOf() 方法向后进行检索（从尾到头），这意味着：假如第二个参数是 50，则从位置 50 开始检索，直到字符串的起点   

### 检索字符串中的字符串   
search() 方法搜索特定值的字符串，并返回匹配的位置    
您注意到了吗？   
两种方法，indexOf() 与 search()，是相等的。   
这两种方法是不相等的。区别在于：   
search() 方法无法设置第二个开始位置参数。   
indexOf() 方法无法设置更强大的搜索值（正则表达式）。   

### 提取部分字符串（slice、substring、substr）   
1、slice() 方法   
slice() 提取字符串的某个部分并在新字符串中返回被提取的部分   
该方法设置两个参数：起始索引（开始位置），终止索引（结束位置）   
如果某个参数为负，则从字符串的结尾开始计数   
2、substring() 方法   
substring() 类似于 slice()    
不同之处在于 substring() 无法接受负的索引  
如果省略第二个参数，则该 substring() 将裁剪字符串的剩余部分     
3、substr() 方法   
substr() 类似于 slice()   
不同之处在于第二个参数规定被提取部分的长度    
如果省略第二个参数，则该 substr() 将裁剪字符串的剩余部分    

### 替换字符串内容   
replace() 方法用另一个值替换在字符串中指定的值    
replace() 方法不会改变调用它的字符串。它返回的是新字符串，默认只替换首个匹配   
replace() 对大小写敏感   
如需执行大小写不敏感的替换，请使用正则表达式 /i（大小写不敏感）：   
str = "Please visit Microsoft!";
var n = str.replace(/MICROSOFT/i, "W3School");   

### 转换为大写和小写   
通过 toUpperCase() 把字符串转换为大写    
通过 toLowerCase() 把字符串转换为小写   

### concat() 方法：concat() 连接两个或多个字符串   
所有字符串方法都会返回新字符串。它们不会修改原始字符串    
正式地说：字符串是不可变的：字符串不能更改，只能替换   

### String.trim()   
trim() 方法删除字符串两端的空白符（Internet Explorer 8 或更低版本不支持 trim() 方法）   
正则去除左右两边空格：str.replace(/^[\s\uFEFF\xA0]+|[\s\uFEFF\xA0]+$/g, '')    

### 提取字符串字符（charAt、charCodeAt）   
1、charAt() 方法：返回字符串中指定下标（位置）的字符串   
2、charCodeAt() 方法：返回字符串中指定索引的字符 unicode 编码    

### 属性访问（Property Access）===== ECMAScript 5 (2009) 允许对字符串的属性访问 [ ]   
var str = "HELLO WORLD";str[0];    

### 把字符串转换为数组：可以通过 split() 将字符串转换为数组   

## JavaScript字符串搜索    
String.indexOf()、String.lastIndexOf()、String.startsWith()、String.endsWith()   
1、String.indexOf()   
indexOf() 方法返回指定文本在字符串中第一次出现（的位置）的索引，不能采用强大的搜索值（正则表达式）   
2、String.lastIndexOf()   
lastIndexOf() 方法返回指定文本在字符串中最后一次出现的索引   
3、String.search()   
search() 方法在字符串中搜索指定值并返回匹配的位置，不能接受第二个起始位置参数   
4、String.match()   
match() 方法根据正则表达式在字符串中搜索匹配项，并将匹配项作为 Array 对象返回   
5、String.includes()   
如果字符串包含指定值，includes() 方法返回 true   








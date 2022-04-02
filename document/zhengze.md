## JavaScript正则表达式   
### 使用字符串方法   
在 JavaScript 中，正则表达式常用于两个字符串方法：search() 和 replace()   
search() 方法使用表达式来搜索匹配，然后返回匹配的位置   
replace() 方法返回模式被替换处修改后的字符串   

### 使用字符串方法 search() 来处理字符串   
search() 方法也接受字符串作为搜索参数。字符串参数将被转换为正则表达式   
var str = "Visit W3School!";var n = str.search("W3School");     

### 在字符串方法 search() 中使用正则表达式   
使用正则表达式执行搜索字符串中 "w3school" 的大小写不敏感的搜索：
var str = "Visit W3School";
var n = str.search(/w3school/i);   

### 使用字符串方法 replace() 处理字符串   
replace() 也接受字符串作为搜索参数   
var str = "Visit Microsoft!";
var res = str.replace("Microsoft", "W3School");    

### 在字符串方法 replace() 中使用正则表达式   
var str = "Visit Microsoft!";
var res = str.replace(/microsoft/i, "W3School");    

### 正则表达式修饰符（修饰符可用于大小写不敏感的更全局的搜素）   
i =====> 执行对大小写不敏感的匹配    
g =====> 执行全局匹配（查找所有匹配而非在找到第一个匹配后停止）   
m =====> 执行多行匹配   

### 正则表达式模式        
1、括号用于查找一定范围的字符串：     
[abc] =====> 查找方括号之间的任何字符   
[0-9] =====> 查找任何从 0 至 9 的数字   
(x|y) =====> 查找由 | 分隔的任何选项   
2、元字符（Metacharacter）是拥有特殊含义的字符：   
\d =====> 查找数字   
\s =====> 查找空白字符   
\b =====> 匹配单词边界   
\uxxxx =====> 查找以十六进制数 xxxx 规定的 Unicode 字符    
3、Quantifiers 定义量词   
n+ =====> 匹配任何包含至少一个 n 的字符串   
n* =====> 匹配任何包含零个或多个 n 的字符串   
n? =====> 匹配任何包含零个或一个 n 的字符串   

### 使用 RegExp 对象   
在 JavaScript 中，RegExp 对象是带有预定义属性和方法的正则表达式对象   

### 使用 test()   
test() 是一个正则表达式方法,它通过模式来搜索字符串，然后根据结果返回 true 或 false   

### 使用 exec()   
exec() 方法是一个正则表达式方法,它通过指定的模式（pattern）搜索字符串，并返回已找到的文本,如果未找到匹配，则返回 null    

完整的正则请参考：https://www.w3school.com.cn/jsref/jsref_obj_regexp.asp



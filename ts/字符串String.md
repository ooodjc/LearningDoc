# 字符串 String

## 语法
```ts
var txt = new String("string");
或者更简单方式：
var txt = "string";
```
---

## 对象属性
### length
> 返回字符串的长度。
```ts
var uname = new String("Hello World") 
console.log("Length "+uname.length)  // 输出 11
```

## 方法
### charAt()
> 返回在指定位置的字符。
```ts
var str = new String("RUNOOB"); 
console.log("str.charAt(0) 为:" + str.charAt(0)); // R
```

### charCodeAt()
> 返回在指定的位置的字符的 Unicode 编码。
```ts
var str = new String("RUNOOB"); 
console.log("str.charCodeAt(0) 为:" + str.charCodeAt(0)); // 82
```

### concat()
> 连接两个或更多字符串，并返回新的字符串。
```ts
var str1 = new String( "RUNOOB" ); 
var str2 = new String( "GOOGLE" ); 
var str3 = str1.concat( str2 ); 
console.log(str3) // RUNOOBGOOGLE
```

### indexOf()
> 返回某个指定的字符串值在字符串中首次出现的位置。
```ts
var str1 = new String( "RUNOOB" ); 
var index = str1.indexOf( "OO" ); 
console.log(index );  // 3
```

### lastIndexOf()
> 从后向前搜索字符串，并从起始位置（0）开始计算返回字符串最后出现的位置。
```ts
var str1 = new String( "This is string one and again string" ); 
var index = str1.lastIndexOf( "string" );
console.log("lastIndexOf 查找到的最后字符串位置 :" + index ); // 29
```

### localeCompare()
> 用本地特定的顺序来比较两个字符串。
```ts
var str1 = new String( "This is beautiful string" );
var index = str1.localeCompare( "This is beautiful string");  
console.log("localeCompare first :" + index );  // 0
```

### match()
> 查找找到一个或多个正则表达式的匹配。
```ts
var str="The rain in SPAIN stays mainly in the plain"; 
var n=str.match(/ain/g);  // ain,ain,ain
```

### replace()
> 替换与正则表达式匹配的子串
```ts
var re = /(\w+)\s(\w+)/; 
var str = "zara ali"; 
var newstr = str.replace(re, "$2, $1"); 
console.log(newstr); // ali, zara
```

### search()
> 检索与正则表达式相匹配的值
```ts
var re = /apples/gi; 
var str = "Apples are round, and apples are juicy.";
if (str.search(re) == -1 ) { 
   console.log("Does not contain Apples" ); 
} else { 
   console.log("Contains Apples" ); 
} 
```

### slice()
> 提取字符串的片断，并在新的字符串中返回被提取的部分。
```ts

```
### split()
> 把字符串分割为子字符串数组
```ts
var str = "Apples are round, and apples are juicy."; 
var splitted = str.split(" ", 3); 
console.log(splitted)  // [ 'Apples', 'are', 'round,' ]
```

### substr()
> 从起始索引号提取字符串中指定数目的字符。
```ts

```

### substring()
> 提取字符串中两个指定的索引号之间的字符。
```ts
var str = "RUNOOB GOOGLE TAOBAO FACEBOOK"; 
console.log("(1,2): "    + str.substring(1,2));   // U
console.log("(0,10): "   + str.substring(0, 10)); // RUNOOB GOO
console.log("(5): "      + str.substring(5));     // B GOOGLE TAOBAO FACEBOOK
```

### toLocaleLowerCase()
> 根据主机的语言环境把字符串转换为小写
```ts
var str = "Runoob Google"; 
console.log(str.toLocaleLowerCase( ));  // runoob google
```

### toLocaleUpperCase()
> 据主机的语言环境把字符串转换为大写
```ts
var str = "Runoob Google"; 
console.log(str.toLocaleUpperCase( ));  // RUNOOB GOOGLE
```

### toLowerCase()
> 把字符串转换为小写。
```ts
var str = "Runoob Google"; 
console.log(str.toLowerCase( ));  // runoob google
```

### toUpperCase()
> 把字符串转换为大写
```ts
var str = "Runoob Google"; 
console.log(str.toUpperCase( ));  // RUNOOB GOOGLE
```

### toString()
> 返回字符串

###

### valueOf()
> 返回指定字符串对象的原始值。
```ts
var str = new String("Runoob"); 
console.log(str.valueOf( ));  // Runoob
```
---
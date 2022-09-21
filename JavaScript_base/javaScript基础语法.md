# ✍初识JavaScirpt

- JavaScript 是世界上最流行的语言之一，是一种运行在客户端的脚本语言 （Script 是脚本的意思）
- 脚本语言：不需要编译，运行过程中由 js 解释器( js 引擎）逐行来进行解释并执行
- 现在也可以基于 Node.js 技术进行服务器端编程

## ✍浏览器执行JS简介

浏览器分成两部分：渲染引擎和 JS 引擎

渲染引擎：用来解析HTML与CSS，俗称内核，比如 chrome 浏览器的 blink ，老版本的 webkit
JS 引擎：也称为 JS 解释器。 用来读取网页中的JavaScript代码，对其处理后运行，比如 chrome 浏览器的 V8
浏览器本身并不会执行JS代码，而是通过内置 JavaScript 引擎(解释器) 来执行 JS 代码 。JS 引擎执行代码时逐行解释每一句源码（转换为机器语言），然后由计算机去执行，所以 JavaScript 语言归为脚本语言，会逐行解释执行。

## ✍JS的组成

JavaScript 包括 ECMAScript、DOM、BOM

### ✍ECMAScript

**ECMAScript** 是由ECMA 国际（ 原欧洲计算机制造商协会）进行标准化的一门编程语言，这种语言在万维网上应用广泛，它往往被称为 JavaScript 或 JScript，但实际上后两者是 ECMAScript 语言的实现和扩展。

ECMAScript：ECMAScript 规定了JS的编程语法和基础核心知识，是所有浏览器厂商共同遵守的一套JS语法工业标准。

### 🔥DOM文档对象模型

文档对象模型（Document Object Model，简称DOM），是W3C组织推荐的处理可扩展标记语言的标准编程接口。通过 DOM 提供的接口可以对页面上的各种元素进行操作（大小、位置、颜色等）。

### 🔥BOM浏览器对象模型

BOM (Browser Object Model，简称BOM) 是指浏览器对象模型，它提供了独立于内容的、可以与浏览器窗口进行互动的对象结构。通过BOM可以操作浏览器窗口，比如弹出框、控制浏览器跳转、获取分辨率等。1、JS初体验🔥

# 1、JS初体验🔥

## 1.1、行内式JS

```html
<input type="button" value="点我试试" onclink="javascript:alert('Hello World')" />
```

1. 可以将单行或少量JS代码写在HTML标签的事件属性中(以on开头的属性)，如： onclink
2. 注意单双引号的使用：在HTML中我们推荐使用**双引号**，JS中我们推荐使用**单引号**
3. 可读性差，在 HTML 中编入 JS 大量代码时，不方便阅读
4. 特殊情况下使用

## 1.2、内嵌式JS🔥

```html
<script>
     alert('Hello World!');
</script>
```

- 可以将多行JS代码写到`<script>`标签中
- 内嵌 JS 是学习时常用的方式

## 1.3、外部JS🔥

```html
<script src="my.js"></script>
```

1. 利于HTML页面代码结构化，把单独JS代码独立到HTML页面之外，既美观，又方便
2. 引用外部JS文件的script标签中间不可以写代码
3. 适合于JS代码量比较大的情况

# 2、JS基本语法🔥

## 2.1、注释🔥

### 2.1.1、单行注释🔥

```js
//  单行注释
```

- 快捷键`ctrl + /`

### 2.1.2、多行注释🔥

```js
/*
	多行注释
*/    
```

- 快捷键 `shift + alt + a`
- vscode中修改快捷键方式：vscode➡ 首选项按钮➡ 键盘快捷方式 ➡ 查找原来的快捷键➡ 修改为新的快捷键➡ 回车确认

## 2.2、输入输出语句🔥

| 方法              | 说明                           | 归属   |
| ----------------- | ------------------------------ | ------ |
| alert(msg);       | 浏览器弹出警示框               | 浏览器 |
| console.log(msg); | 浏览器控制台打印输出信息       | 浏览器 |
| prompt(info);     | 浏览看弹出输入框，用户可以输入 | 浏览器 |

alert() 主要用来显示消息给用户
console.log() 用来给程序员看自己运行时的消息

## 2.3、变量🔥

变量是用于存放数据的容器，我们通过变量名获取数据，甚至数据可以修改

本质：变量是程序在内存中申请的一块用来存放数据的空间

### 2.3.1、变量初始化🔥

1. var是一个JS关键字，用来声明变量(variable变量的意思)。使用该关键字声明变量后，计算机会自动为变量分配内存空间。

2. age 是程序员定义的变量名，我们要通过变量名来访问内存中分配的空间

```js
//声明变量同时赋值为18
var age = 18; 
//同时声明多个变量时，只需要写一个 var， 多个变量名之间使用英文逗号隔开。

var age = 18, address ='火影村',salary = 15000;
```

### 2.3.2、声明变量特殊情况🔥

| 情况                       | 说明                   | 结果      |
| -------------------------- | ---------------------- | --------- |
| var age; console.log(age); | 只声明，不赋值         | undefined |
| console.log(age)           | 不声明 不赋值 直接使用 | 报错      |
| age = 10;console.log(age); | 不声明 只赋值          | 10        |

### 2.3.3、变量的命名规范🔥

1. 由字母(A-Z,a-z)，数字(0-9)，下划线(_)，美元符号($)组成，如:usrAge,num01,__name
2. 严格区分大小写。 var app; 和 var App; 是两个变量
3. 不能以数字开头。
4. 不能是关键字，保留字。例如：var,for,while
5. 遵循驼峰命名法。首字母小写，后面单词的首字母需要大写。myFirstName
6. 推荐翻译网站：有道 爱词霸

## 2.4、数据类型🔥

**JavaScript** **是一种弱类型或者说动态语言。**这意味着不用提前声明变量的类型，在程序运行过程中，类型会被自动确定。

```js
var age = 10; 			 //这是一个数字型
var areYouOk = '使得';	//这是一个字符串
```

- 在代码运行时，变量的数据类型是由 JS引擎 根据 = 右边变量值的数据类型来判断 的，运行完毕之后， 变量就确定了数据类型。
- JavaScript 拥有动态类型，同时也意味着相同的变量可用作不同的类型

```js
var x = 6;		//x为数字
var x = "Bill";	//x为字符串
```

JS 把数据类型分为两类：

- 基本数据类型(Number,String,Boolean,Undefined,Null)
- 复杂数据类型(Object)

### 2.4.1、基本数据类型🔥

| 简单数据类型 | 说明                                            | 默认值                |
| ------------ | ----------------------------------------------- | --------------------- |
| Number       | 数字型，包含整型值和浮点型值，如21，0.21        | 0                     |
| Boolean      | 布尔值类型，如true，false ，等价于1和0          | false                 |
| Undefined    | var a; 声明了变量a但是没有赋值，此时a=undefined | undefined（未定义的） |
| string       | 字符串类型，如“张三”                            | “”                    |
| Null         | var a = null;声明了变量a为空值                  | null                  |

### 2.4.2、数字型Number

JavaScript 数字类型既可以用来保存整数值，也可以保存小数(浮点数）。

```js
var age = 12;		//整数
var Age = 21.3747;	//小数
```

### 2.4.2、数字型进制🔥

最常见的进制有二进制、八进制、十进制、十六进制。

```js
// 1.八进制数字序列范围：0~7
var num1 = 07; 		//对应十进制的7
var Num2 = 019;		//对应十进制的19
var num3 = 08;		//对应十进制的8


// 2.十六进制数字序列范围：0~9以及A~F
var num = 0xA;
```

- **在JS中八进制前面加0，十六进制前面加 0x**

#### ①数字型范围🔥

- JS中数值的最大值：`Number.MAX_VALUE`
- JS中数值的最小值：`Number.MIN_VALUE`

```html
consol.log(Number.MAX_VALUE);
consol.log(Number.MIN_VALUE);
```

#### ②数字型的三个特殊值🔥

```js
alert(Infinity); 	//Infinity(无穷大)
alert(-Infinity); 	//-Infinity(无穷小)
alert(NaN);       	//NaN - Not a Number ,代表任何一个非数值
```

- Infinity ，代表无穷大，大于任何数值
- -Infinity ，代表无穷小，小于任何数值
- Nan ，Not a Number，代表一个非数值

#### ③isNaN🔥

这个方法用来判断非数字，并且返回一个值，如果是数字返回的是false，如果不是数字返回的是true

![](https://victor-gx.oss-cn-beijing.aliyuncs.com/img/2022/js/202208160943261.png)

```js
var userAge = 21;
var isOk = isNan(userAge);
console.log(isOk);		//false,21不是一个非数字

var userName = "andy";
console.log(isNan(userName));	//true,"andy"是一个非数字
```

### 2.4.3、字符串型String🔥

字符串型可以是引号中的任意文本，其语法为 “**双引号**” 和 "**单引号**’’

```js
var strMsg = "我爱北京天安门~";		//使用双引号表示字符串
var strMsg = '我爱北京';			  //使用单引号表示字符串
```

因为 HTML 标签里面的属性使用的是双引号，JS 这里我们更推荐**使用单引号**。

#### ①字符串引号嵌套🔥

JS可以用 **单引号嵌套双引号**，或者用 **双引号嵌套单引号**（**外双内单，外单内双**）

```js
var strMsg ='我是一个“高富帅”' //可以用 ' ' 包含 " "
var strMsg2 ="我是'高富帅'" //可以用" "  包含  ''
```

#### ②字符串转义符🔥

类似HTML里面的特殊字符，字符串中也有特殊字符，我们称之为转义符。

转义符都是 \ 开头的，常用的转义符及其说明如下：

| 转义符 | 解释说明             |
| ------ | -------------------- |
| \n     | 换行符，n是newline   |
| \ \    | 斜杠\                |
| \ ’    | ’ 单引号             |
| \ ‘’   | ‘’ 双引号            |
| \ t    | tab 缩进             |
| \ b    | 空格，b是blank的意思 |

#### ③字符串长度🔥

字符串是由若干字符组成的，这些字符的数量就是字符串的长度。通过字符串的 length 属性可以获取整个字符串的长度。

```js
//通过字符串的length属性可以获取整个字符串的长度
var strMsg = "我是高富帅！";
alert(strMsg.length);     //显示6
```

#### ④字符串的拼接🔥

- 多个字符串之间可以使用 + 进行拼接，其拼接方式为 **字符串 + 任何类型 = 拼接之后的新字符串**
- 拼接前会把与字符串相加的任何类型转成字符串，再拼接成一个新的字符串

**注意**：字符串 + 任何类型 =拼接之后的新字符串

```js
//1 字符串相加
alert('hello' + ' ' + 'World');  //hello World

//2 数值字符串相加
alert('100' + '100'); //100100

//3 数值字符串+数值
alert('12'+12); //1212

//4 数值+数值
alert(12+12); //24
```

- `+` 号总结口诀：🌏数值相加，字符相连🌏

```js
var  age = 18;
console.log('我今年'+age+'岁');
console.log('我今年'+age+'岁');  //引引加加，最终也是上面的形式
```

⑤字符串拼接加强🔥

```js
console.log('Pink老师' + 18);			//只要有字符就会相连
var age = 18;
// console.log('Pink老师age岁了');		//这样不行,会输出 "Pink老师age岁了"

console.log('Pink老师' + age);		 // Pink老师18
console.log('Pink老师' + age + '岁啦');	// Pink老师18岁啦
```

- 我们经常会将字符串和变量来拼接，因为变量可以很方便地修改里面的值
- 变量是不能添加引号的，因为加引号的变量会变成字符串
- 如果变量两侧都有字符串拼接，口诀==🌏“引引加加 ”，删掉数字🌏==变量写加中间

### 2.4.4、布尔型Boolean🔥

- 布尔类型有两个值：true 和 false ，其中 true 表示真（对），而 false 表示假（错）。
- 布尔型和数字型相加的时候， true 的值为 1 ，false 的值为 0。

```js
var flag = true;
console.log(flag + 1); // 2 true当加法来看当1来看，flase当0来看
```

### 2.4.5、undefined未定义🔥

- 一个**声明后没有被赋值**的变量会有一个默认值 undefined ( 如果进行相连或者相加时，注意结果）

```js
// 如果一个变量声明未赋值，就是undefined 未定义数据类型
var str;
console.log(str);				//undefined
var variable = undefined;
console.log(variable + 'Pink'); //undefinedPink
console.log(variable + 18); //NaN 
```

1.undefined 和 字符串 相加，会拼接字符串

2.undefined 和 数字相加，最后结果是**NaN**

### 2.4.6、空值null🔥

- 一个声明变量给 null 值，里面存的值为空

```js
var space = null;
console.log(space + 'pink'); //nullpink
console.llog(space + 1); // 1 
```

### 2.4.7、typeof🔥

- typeof 可用来获取检测变量的数据类型

```js
var num = 18;
console.log(typeof num) // 结果 number  
```

不同类型的返回值

| 类型      | 例               | 结果        |
| --------- | ---------------- | ----------- |
| string    | typeof “小白”    | “string”    |
| number    | typeof 18        | “number”    |
| boolean   | typeof true      | “boolean”   |
| undefined | typeof undefined | “undefined” |
| null      | typeof null      | “object”    |

### 2.4.8、字面量

字面量是在源代码中一个固定值的表示法，通俗来说，就是字面量表示如何表达这个值。

- 数字字面量：8，9，10
- 字符串字面量：‘大前端’，‘后端’
- 布尔字面量：true、false

通过控制台的颜色判断属于哪种数据类型

| 黑色 | 字符串            |
| ---- | ----------------- |
| 蓝色 | 数值              |
| 灰色 | undefined 和 null |

## 2.5、数据类型转换🔥

使用表单、prompt 获取过来的数据默认是字符串类型的，此时就不能直接简单的进行加法运算，而需要转换变量的数据类型。通俗来说，**就是把一种数据类型的变量转换成另外一种数据类型**。

我们通常会实现3种方式的转换：

- 转换为字符串类型
- 转换为数字型
- 转换为布尔型

### ①转换为字符串型🔥

| 方式               | 说明                         | 案例                                 |
| ------------------ | ---------------------------- | ------------------------------------ |
| toString()         | 转成字符串                   | var num = 1; alert(num.toString());  |
| String()强制转换   | 转成字符串                   | var num = 1; alert(String(num));     |
| **加号拼接字符串** | 和字符串拼接的结果都是字符串 | var num =1; alert(num+“我是字符串”); |

```js
//1.把数字型转换为字符串型 toString()  变量.toString()
var num = 10;
var str = num.toString();
console.log(str);

//2.强制转换
console.log(String(num));
```

- toString() 和 String() 使用方式不一样
- 三种转换方式，我们更喜欢用第三种加号拼接字符串转换方式，这一方式也称为隐式转换

### ②转换为数字型🔥

| 方式                       | 说明                         | 案例                |
| -------------------------- | ---------------------------- | ------------------- |
| **parselnt(string)函数**   | 将string类型转成整数数值型   | parselnt(‘78’)      |
| **parseFloat(string)函数** | 将string类型转成浮点数数值型 | parseFloat(‘78.21’) |
| Number()强制转换函数       | 将string类型转换为数值型     | Number(‘12’)        |
| js 隐式转换(- * /)         | 利用算术运算隐式转换为数值型 | ‘12’-0              |

```js
// 1.parseInt()
var age =prompt('请输入您的年龄');
consolo.log(parseInt(age));  //数字型18
consolo.log(parseInt('3.14'));  //3取整
consolo.log(parseInt('3.94'));  //3,不会四舍五入
consolo.log(parseInt('120px'));  //120,会去掉单位

// 2.parseFloat()
console.log(parseFloat('3.14'));  //3.14
consolo.log(parseFloat('120px'));  //120,会去掉单位


// 3.利用Number(变量)
var str ='123';
console.log(Number(str));
console.log(Number('12'));   

// 4.利用了算术运算 - * /   隐式转换
console.log('12'-0);  // 12
console.log('123' - '120');  //3
console.log('123' * 1);  // 123
```

### ③转换为布尔型

| 方法          | 说明               | 案例             |
| ------------- | ------------------ | ---------------- |
| Boolean()函数 | 其他类型转成布尔值 | Boolean(‘true’); |

- 代表空，否定的值会被转换为false，如 ’ ’ , 0, NaN , null , undefined
- 其余的值都会被被转换为true

```js
console.log(Boolean('')); //false
console.log(Boolean(0));  //false
console.log(Boolean(NaN)); //false
console.log(Boolean(null)); //false
console.log(Boolean(undefined)); //false
console.log(Boolean('小白')); //true
console.log(Boolean(12));   //true
```

## 2.6、运算符🔥

运算符（operator）也被称为**操作符**，是用于实现赋值、比较和执行算数运算等功能的符号

JavaScript 中常用的运算符有：

- 算数运算符
- 递增和递减运算符
- 比较运算符
- 逻辑运算符
- 赋值运算符

### 2.6.1、算术运算符🔥

概念：算术运算使用的符号，用于执行两个变量或值的算术运算。

| 运算符 | 描述           | 实例                    |
| ------ | -------------- | ----------------------- |
| +      | 加             | 10 + 20 =30             |
| -      | 减             | 10 - 20 =-10            |
| *      | 乘             | 10 * 20 =200            |
| /      | 除             | 10 / 20 =0.5            |
| %      | 取余数（取模） | 返回出发的余数 9 % 2 =1 |

### 2.6.2、浮点数的精度问题🔥

浮点数值的最高精度是17位小数，但在进行算数计算时其精确度远远不如整数

```js
var result = 0.1 +0.2; //结果不是0.3，0.30000000000000004
console.log(0.07 * 100); //结果不是7，而是7.000000000000001
```

**所以不要直接判断两个浮点数是否相等**

### 2.6.3、递增和递减运算符🔥

递增（++）

递减（- -）

放在变量前面时，我们称为**前置递增(递减)运算符**

放在变量后面时，我们称为**后置递增(递减)运算符**

**注意**：递增和递减运算符必须和变量配合使用。

#### ①前置递增运算符🔥

`++num` 等价于`num = num + 1`

使用口诀:**先自加，后返回值**

```js
var num = 10;
alert (++num + 10); // 21
```

先自加 10+1=11，返回11，此时num=11

#### ②后置递增运算符🔥

num ++ num = num +1

使用口诀:**先返回原值，后自加**

```js
var num = 10;
alert(10 + num++); // 20
```

#### ③小结🔥

- 前置递增和后置递增运算符可以简化代码的编写，让变量的值 + 1 比以前写法更简单
- 单独使用时，运行结果相同，与其他代码联用时，执行结果会不同
- 开发时，大多使用后置递增/减，并且代码独占一行

### 2.6.4、比较(关系)运算符🔥

比较运算符是**两个数据进行比较时所使用的运算符**，比较运算后，会**返回一个布尔值**(true / false)作为比较运算的结果。

| 运算符名称 | 说明                        | 案例        | 结果  |
| ---------- | --------------------------- | ----------- | ----- |
| <          | 小于号                      | 1 < 2       | true  |
| >          | 大于号                      | 1 > 2       | false |
| >=         | 大于等于号(大于或者等于)    | 2 >= 2      | true  |
| <=         | 小于等于号(小于或者等于)    | 3 <= 2      | false |
| ==         | 判等号(会转型)              | 37 == 37    | true  |
| !=         | 不等号                      | 37 != 37    | false |
| === !==    | 全等 要求值和数据类型都一致 | 37 === ‘37’ | false |

#### ①=、==、=== 小结

| 符号 | 作用 | 用法                                   |
| ---- | ---- | -------------------------------------- |
| =    | 赋值 | 把右边给左边                           |
| ==   | 判断 | 判断两边值是否相等(注意此时有隐士转换) |
| ===  | 全等 | 判断两边的值和数据类型是否完全相同     |

```js
console.log(18 == '18');		//true
console.log(18 === '18');		//false
```

### 2.6.5、逻辑运算符🔥

逻辑运算符是用来进行布尔值运算的运算符，其返回值也是布尔值

| 逻辑运算符 | 说明                   | 案例            |
| ---------- | ---------------------- | --------------- |
| &&         | “逻辑与”，简称"与" and | true && false   |
| \|\|       | “逻辑或”，简称"或" or  | true \|\| false |
| ！         | “逻辑非”，简称"非" not | ！true          |

逻辑与：两边都是 true才返回 true，否则返回 false

逻辑或：两边都为 false 才返回 false，否则都为true

逻辑非：逻辑非（!）也叫作取反符，用来取一个布尔值相反的值，如 true 的相反值是 false

```js
var isOk = !true;
console.log(isOk);  // false
//逻辑非（!）也叫作取反符，用来取一个布尔值相反的值，如 true 的相反值是 false
```

#### 2.6.5.1、短路运算(逻辑中断)🔥

短路运算的原理：当有多个表达式（值）时,左边的表达式值可以确定结果时,就不再继续运算右边的表达式的值

##### ①逻辑与🔥

- 语法：表达式1 && 表达式2
- 如果第一个表达式的值为真，则返回表达式2
- 如果第一个表达式的值为假，则返回表达式1

```js
console.log(123 && 456);   //456
console.log(0 && 456);     //0
console.log(123 && 456 && 789);  //789
```

##### ②逻辑或

- 语法：表达式1 || 表达式2
- 如果第一个表达式的值为真，则返回表达式1
- 如果第一个表达式的值为假，则返回表达式2

```js
console.log(123 || 456); //123
console.log(0 || 456);   //456
console.log(123 || 456 || 789);  //123
var num = 0;
console.log(123 || num++);
// 先返回在加，相当于 (123 || 0)
console.log(num);    // 123
```

### 2.6.6、赋值运算符🔥

概念：用来把数据赋值给变量的运算符。

| 赋值运算符 | 说明                 | 案例                        |
| ---------- | -------------------- | --------------------------- |
| =          | 直接赋值             | var usrName = ‘我是值’      |
| += ，-=    | 加，减一个数后再赋值 | var age = 10； age+=5；//15 |
| *=，/=，%= | 成，除，取模后再赋值 | var age = 2; age*=5; //10   |

```js
var age = 10;
age += 5;  // 相当于 age = age + 5;
age -= 5;  // 相当于 age = age - 5;
age *= 10; // 相当于 age = age * 10;
```

### 2.6.7、运算符优先级🔥

| 优先级 | 运算符     | 顺序                          |
| ------ | ---------- | ----------------------------- |
| 1      | 小括号     | ()                            |
| 2      | 一元运算符 | ++ – ！                       |
| 3      | 算数运算符 | **先 \* / 后 + -**            |
| 4      | 关系运算符 | **>, >= , < , <=**,           |
| 5      | 相等运算符 | ，！=，=，！==                |
| 6      | 逻辑运算符 | **先 && 后 \|\|（先与后或）** |
| 7      | 赋值运算符 | =                             |
| 8      | 逗号运算符 | ，                            |

1. 一元运算符里面的**逻辑非**优先级很高

2. **逻辑与** 比 **逻辑或** 优先级高

3. 练习题

```js
console.log( 4 >= 6 || '人' != '阿凡达' && !(12 * 2 == 144) && true)	// true
var a = 3 > 5 && 2 < 7 && 3 == 4; 
console.log(a); 	//false 

var b = 3 <= 4 || 3 > 1 || 3 != 2; 
console.log(b); 	//true

var c = 2 === "2"; 
console.log(c);  	//false

var d = !c || b && a ;
console.log(d);		//true
```

## 2.7、流程控制🔥

流程控制主要有三种结构，分别是顺序结构、分支结构和循环结构，这三种结构代表三种代码执行的顺序

### 2.7.1、分支结构🔥

JS 语言提供了两种分支结构语句：**JS 语句** **switch语句**

#### ①if语句🔥

```js
// 条件成立执行代码，否则什么也不做
if (条件表达式) {
    //条件成立执行的代码语句
}
```

>  案例：进入网吧
>
> 弹出一个输入框，要求用户输入年龄，如果年龄大于等于 18 岁，允许进网吧

```js
var usrAge = prompt('请输入您的年龄:');
if(usrAge >= 18)
{
      alert('您的年龄合法，欢迎来到老子网吧享受学习的乐趣！');
}
```

#### ②if else 语句🔥

```js
// 条件成立，执行if里面代码，否则执行else里面的代码
if(条件表达式)
{
    //[如果]条件成立执行的代码
}
else
{
    //[否则]执行的代码
}
```

> 案例：判断闰年
>
> 接收用户输入的年份，如果是闰年就弹出闰年，否则弹出是平年

**算法**：能被4整除且不能整除100的为闰年（如2004年就是闰年，1901年不是闰年）或者能够被 400 整除的就是闰年

```js
var year = prompt('请输入年份');

if (year % 4 == 0 && year % 100 !=0 || year % 400 ==0)
{
   alert('这个年份是闰年');
}
else
{
  alert('这个年份是平年');
}
```

#### ③if else if 语句🔥

```js
if(条件表达式1)
{
  语句1;
}
else if(条件表达式2)
{
   语句2;
}
else if(条件表达式3)
{
  语句3;
}
else
{
   //上述条件都不成立执行此处代码
}
```

> 案例:接收用户输入的分数，根据分数输出对应的等级字母 A、B、C、D、E
>
> 其中：
>
> 90分(含)以上 ，输出：A
>
> 80分(含)~ 90 分(不含)，输出：B
>
> 70分(含)~ 80 分(不含)，输出：C
>
> 60分(含)~ 70 分(不含)，输出：D
>
> 60分(不含) 以下，输出： E

```js
 var score = prompt('请您输入分数:');
        if (score >= 90) {
            alert('宝贝，你是我的骄傲');
        } else if (score >= 80) {
            alert('宝贝，你已经很出色了');
        } else if (score >= 70) {
            alert('你要继续加油喽');
        } else if (score >= 60) {
            alert('孩子，你很危险');
        } else {
            alert('可以再努力点吗，你很棒，但还不够棒');
        }
```

### 2.7.2、三元表达式🔥

- 语法结构 : 表达式1 ? 表达式2 : 表达式3
- 执行思路

如果表达式1为true，则返回表达式2的值,如果表达式1为false，则返回表达式3的值

> 案例：数字补0
>
> 用户输入数字，如果数字小于10，则在前面补0，比如01，09，如果数字大于10，则不需要补，比如20

```js
var figuer = prompt('请输入0~59之间的一个数字');
        var result = figuer < 10 ? '0' + figuer : figue
        alert(result);
```

### 2.7.3、switch🔥

```js
switch(表达式){
  case value1:
     //表达式等于 value1 时要执行的代码
     break;
  case value2:
     //表达式等于value2 时要执行的代码
     break;
  default:
     //表达式不等于任何一个value时要执行的代码
        
}
```

- switch ：开关 转换 ， case ：小例子 选项
- 关键字 switch 后面括号内可以是表达式或值， 通常是一个变量
- 关键字 case , 后跟一个选项的表达式或值，后面跟一个冒号
- switch 表达式的值会与结构中的 case 的值做比较
- 如果存在匹配全等(===) ，则与该 case 关联的代码块会被执行，并在遇到 break 时停止，整个 switch 语句代码执行结束
- 如果所有的 case 的值都和表达式的值不匹配，则执行 default 里的代码
- 执行case 里面的语句时，如果没有break，则继续执行下一个case里面的语句

```js
// 用户在弹出框里面输入一个水果，如果有就弹出该水果的价格， 如果没有该水果就弹出“没有此水果”
        var fruit = prompt('请您输入查询的苹果');
        switch (fruit) {
            case '苹果':
                alert('苹果的价格为3.5元/千克');
                break;
            case '香蕉':
                alert('香蕉的价格为3元/千克');
                break;
            default:
                alert('没有这种水果');
        }

```

# 3、断点调试🔥

1. 浏览器中按 F12–> sources -->找到需要调试的文件–>在程序的某一行设置断点(在行数点一下)
2. 刷新浏览器
3. Watch: 监视，通过watch可以监视变量的值的变化，非常的常用
4. F11: 程序单步执行，让程序一行一行的执行，这个时候，观察watch中变量的值的变化

# 4、循环🔥

## 4.1、for循环🔥

在程序中，一组被重复执行的语句被称之为**循环体**，能否继续重复执行，取决于循环的**终止条件**。由循环体及循环的终止条件组成的语句，被称之为**循环语句**

```js
for(初始化变量;条件表达式;操作表达式)
{
   //循环体
}
```

**1.输入10句"I love you！"**

```js
//基本写法
for(var i = 1; i<=10; i++  )
    {
         console.log('I love you！');
    }
// 用户输入次数
var num = prompt('请输入次数:');
for(var i = 1; i<= num ;i++)
    {
        console.log('I love you！');
    }

```

**2.求1-100之间所有整数的累加和**

```js
// 求1-100所以的整数和
var sum = 0;
for (var i = 1; i <= 100; i++) {
    var sum = sum + i;
}
console.log(sum);
```

**3.求1-100之间所有数的平均值**

```js
 // 3.求1-100之间所有数的平均值
var sum = 0;
for (var i = 1; i <= 100; i++) {
    var sum = sum + i;
}
console.log(sum / 100);
```

**4.求1-100之间所有偶数和奇数的和**

```js
//    4.求1-100之间所有偶数和奇数的和
var sum1 = 0;
var sum2 = 0;
for (var i = 1; i <= 100; i++) {
    if (i % 2 == 0) {
        sum1 = sum1 + i;
    } else {
        sum2 = sum2 + i;
    }
}
console.log('偶数和为' + sum1);
console.log('奇数和为' + sum2);
```

**5.求1-100之间所有能被3整除的数字的和**

```js
// 5.求1-100之间所有能被3整除的数字的和
var sum = 0;
for (var i = 1; i <= 100; i++) {
    if (i % 3 == 0) {
        sum += i;
    }
}
console.log(sum);
```

**6.要求用户输入班级人数，之后依次输入每个学生的成绩，最后打印出该班级总的成绩以及平均成绩。**

```js
var num = prompt('请输入班级总的人数:'); // num 班级总的人数
var sum = 0; // 总成绩
var average = 0; // 平均成绩
for (var i = 1; i <= num; i++) {
     var score = prompt('请输入第' + i + '个学生的成绩');
    //这里接收的是str，必须转换为数值
     sum = sum + parseFloat(score);         
}
average = sum / num;
alert('班级总的成绩是：' + sum);
alert('班级总的平均成绩是：' + average);
```

**7.一行打印5个星星**

我们采取追加字符串的方式，这样可以打印到控制台上

```js
var star = '';
for (var i = 1; i <= 5; i++) {
     star += '☆';
 }
console.log(star);
```

## 4.2、双重for循环🔥

**循环嵌套**是指在一个循环语句中再定义一个循环语句的语法结构，例如在for循环语句中，可以再嵌套一个for 循环，这样的 for 循环语句我们称之为双重for循环。

```js
for(外循环的初始;外循环的条件;外形循环的操作表达式){
    for(内循环的初始;内循环的条件;内循环的操作表达式){
        需执行的代码;
    }
}
```

- 内层循环可以看做外层循环的语句
- 内层循环执行的顺序也要遵循 for 循环的执行顺序
- 外层循环执行一次，内层循环要执行全部次数

### ①打印五行五列星星

核心：

- 内层循环负责一行打印五个星星
- 外层循环负责打印五行

```js
var star = '';
for(var j = 1;j<=5;j++)
{
   for (var i = 1; i <= 5; i++)
   {
     star += '☆'
   }
    //每次满5个星星就加一次换行
    star +='\n'  
}
console.log(star);
```

### ②打印n行n列的星星

要求用户输入行数和列数，之后在控制台打印出用户输入行数和列数的星星

```js
var star = '';
var row = prompt('请输入行数');
var col = prompt('请输入列数');
for (var j = 1; j <= col; j++) {
    for (var i = 1; i <= row; i++) {
        star += '☆';
    }
    star += '\n';
}
console.log(star);
```

### ③打印倒三角形

- 一共有10行，但是每行的星星个数不一样，因此需要用到双重 for 循环
- 外层的 for 控制行数 i ，循环10次可以打印10行
- 内层的 for 控制每行的星星个数 j
- 核心算法： 每一行星星的个数： j = i ; j <= 10; j++
- 每行打印完毕后，都需要重新换一行

```js
var star = '';
var row = prompt('请输入行数');
var col = prompt('请输入列数');
for (var i = 1; i <= row; i++) {
    for (var j = i; j <= col; j++) {
        star += '☆';
    }
    star += '\n';
}
console.log(star);
```

## 4.3、while循环🔥

```js
while(条件表达式){
  //循环体代码
}
```

执行思路：

- 先执行条件表达式，如果结果为 true，则执行循环体代码；如果为 false，则退出循环，执行后面代码
- 执行循环体代码
- 循环体代码执行完毕后，程序会继续判断执行条件表达式，如条件仍为true，则会继续执行循环体，直到循环条件为 false 时，整个循环过程才会结束

**注意**：

- 使用 while 循环时一定要注意，它必须要有退出条件，否则会称为死循环
- while 循环和 for 循环的不同之处在于 while 循环可以做较为复杂的条件判断，比如判断用户名和密码

### ①打印人的一生

从1岁到99岁

```js
var age = 0;
while (age <= 100) {
    age++;
    console.log('您今年' + age + '岁了');
}
```

### ②计算 1 ~ 100 之间所有整数的和

```js
var figure = 1;
        var sum = 0;
        while (figure <= 100) {
            sum += figure;
            figure++;
        }
console.log('1-100的整数和为' + sum);
```

## 4.4、do while循环🔥

执行思路：

1. 先执行一次循环体代码
2. 再执行表达式，如果结果为true，则继续执行循环体代码，如果为false，则退出循环，继续执行后面的代码
3. 先执行再判断循环体，**所以dowhile循环语句至少会执行一次循环体代码**

**需求：弹出一个提示框， 你爱我吗？ 如果输入我爱你，就提示结束，否则，一直询问**

```js
do {
	var love = prompt('你爱我吗？');
} while (love != '我爱你');
	alert('登录成功');
```

## 4.5、continue 关键字🔥

continue 关键字用于**立即跳出本次循环，继续下一次循环**（本次循环体中 continue 之后的代码就会少执行一次）。

例如，吃5个包子，第3个有虫子，就扔掉第3个，继续吃第4个第5个包子

```js
for (var i = 1; i <= 5; i++) {
 if (i == 3) {
     console.log('这个包子有虫子，扔掉');
     continue; // 跳出本次循环，跳出的是第3次循环 
  }
  console.log('我正在吃第' + i + '个包子呢');
}
```

## 4.6、break关键字🔥

break 关键字用于**立即跳出整个循环**

例如，吃5个包子，吃到第3个发现里面有半个虫子，其余的也不吃了

```js
for (var i = 1; i <= 5; i++) {
   if (i == 3) {
       break; // 直接退出整个for 循环，跳到整个for下面的语句
   }
   console.log('我正在吃第' + i + '个包子呢');
 }
```

# 5、数组🔥

数组(Array)是指一组数据的集合，其中的每个数据被称作元素，在数组中可以存放任意类型的元素。数组是一种将一组数据存储在单个变量名下的优雅方式

```js
//普通变量一次只能存储一个值
var num = 10;
//数组一次可以存储多个值
var arr =[1,2,3,4,5];
```

## 5.1、创建数组🔥

JavaScript 中创建数组有两种方式：

- 利用 new 创建数组
- 利用数组字面量创建数组

### ①利用 new 创建数组🔥

```js
var 数组名 = new Array();
var arr = new Array(); //创建一个新的空数组
```

- 这种方式暂且了解，等学完对象再看
- 注意 `Array()`，A要大写

### ②利用数组字面量创建数组🔥

```js
// 1.利用数组字面量方式创建空的数组 
var 数组名 =[];
// 2.使用数组字面量方式创建带初始值的数组
var 数组名 =['小白','小黑','小黄','瑞奇'];
// 3.数组中可以存放任意类型的数据，例如字符串，数字，布尔值等
var arrStus =['小白'，12,true,28.9];
```

- 数组的字面量是方括号 `[]`
- 声明数组并赋值称为数组的初始化
- 这种字面量方式也是我们以后最多使用的方式

## 5.2、数组的索引（下标）🔥

索引 (下标) ：用来访问数组元素的序号（数组下标从 0 开始）

```js
//定义数组
var arrStus = [1,2,3];
//获取数组中的第2个元素
alert(arrStus[1]);
```

## 5.3遍历数组🔥

我们可以通过 for 循环索引遍历数组中的每一项

```js
// 数组索引访问数组中的元素
var arr = ['red','green', 'blue'];
console.log(arr[0]) // red
console.log(arr[1]) // green
console.log(arr[2]) // blue

// for循环遍历数组
var arr = ['red','green', 'blue'];
for (var i = 0; i < arr.length; i++){
    console.log(arrStus[i]);
}
```

## 5.4、数组的长度🔥

使用“数组名.length”可以访问数组元素的数量（数组长度）

```js
var arrStus = [1,2,3];
alert(arrStus.length);  // 3
```

**注意**：

- 此处数组的长度是**数组元素的个数** ，不要和**数组的索引号**混淆
- 当我们数组里面的元素个数发生了变化，这个 length 属性跟着一起变化

## 5.5、案例

**1.请将 [“关羽”,“张飞”,“马超”,“赵云”,“黄忠”,“刘备”,“姜维”]; 数组里的元素依次打印到控制台**

```js
var arr = ["关羽","张飞","马超","赵云","黄忠","刘备","姜维"]; 
// 遍历  从第一个到最后一个
for(var i = 0; i < arr.length; i++ )  { 
   console.log( arr[i] );
} 
```

**2.求数组 [2,6,1,7, 4] 里面所有元素的和以及平均值**

- 声明一个求和变量 sum。
- 遍历这个数组，把里面每个数组元素加到 sum 里面。
- 用求和变量 sum 除以数组的长度就可以得到数组的平均值。

```js
var arr = [2, 6, 1, 7, 4];
var sum = 0;
var average = 0;
for (var i = 0; i < arr.length; i++) {
    sum += arr[i];
}
average = sum / i; //此时i为5
//      average = sum / arr.length;
console.log('和为' + sum);
console.log('平均值为' + average);
```

3.求数组[2,6,1,77,52,25,7]中的最大值

- 声明一个保存最大元素的变量 max。
- 默认最大值可以取数组中的第一个元素。
- 遍历这个数组，把里面每个数组元素和 max 相比较。
- 如果这个数组元素大于max 就把这个数组元素存到 max 里面，否则继续下一轮比较。
- 最后输出这个 max。

```js
 var arr = [2, 6, 1, 77, 52, 25, 7];
        var max = arr[0];
        var temp;
        for (var i = 0; i < arr.length; i++) {
            if (max < arr[i]) {
                temp = max;
                max = arr[i];
                arr[i] = temp;
            }
        }
        console.log('最大值为' + max);


方法二：

var arrNum = [2,6,1,77,52,25,7];
var maxNum = arrNum[0]; // 用来保存最大元素,默认最大值是数组中的第一个元素
// 从0 开始循环数组里的每个元素
for(var i = 0;i< arrNum.length; i++){
    // 如果数组里当前循环的元素大于 maxNum，则保存这个元素和下标
    if(arrNum[i] > maxNum){
        maxNum = arrNum[i]; // 保存数值到变量 maxNum
    }
}
```

**4.将数组 [‘red’, ‘green’, ‘blue’, ‘pink’] 里面的元素转换为字符串**

思路：就是把里面的元素相加就好了，但是注意保证是字符相加

- ①需要一个新变量 str 用于存放转换完的字符串。
- ②遍历原来的数组，分别把里面数据取出来，加到字符串变量 str 里面。

```js
var arr = ['red','green','blue','pink'];
var str ='';
for(var i = 0; i < arr.length; i++){
    str += arr[i];
}
console.log(str);
// redgreenbluepink
```

**5.将数组 [‘red’, ‘green’, ‘blue’, ‘pink’] 转换为字符串，并且用 | 或其他符号分割**

- ①需要一个新变量用于存放转换完的字符串 str。
- ①遍历原来的数组，分别把里面数据取出来，加到字符串里面。
- ①同时在后面多加一个分隔符

```js
var arr = ['red', 'green', 'blue', 'pink'];
var str = '';
var separator = '|';
for (var i = 0; i < arr.length; i++) {
   str += arr[i] + separator;
}
console.log(str);
// red|green|blue|pink
```

## 5.6、数组中新增元素🔥

### ①通过修改 length 长度新增数组元素

- 可以通过修改 length 长度来实现数组扩容的目的
- length 属性是可读写的

```js
var arr = ['red', 'green', 'blue', 'pink'];
arr.length = 7;
console.log(arr);
console.log(arr[4]);
console.log(arr[5]);
console.log(arr[6]);
```

其中索引号是 4，5，6 的空间没有给值，就是声明变量未给值，默认值就是 **undefined**

### ②通过修改数组索引新增数组元素

- 可以通过修改数组索引的方式追加数组元素
- 不能直接给数组名赋值，否则会覆盖掉以前的数据
- 这种方式也是我们最常用的一种方式

```js
var arr = ['red', 'green', 'blue', 'pink'];
arr[4] = 'hotpink';
console.log(arr);
```

## 5.7、数组中新增元素

**1.新建一个数组，里面存放10个整数（ 1~10）， 要求使用循环追加的方式输出： [1,2,3,4,5,6,7,8,9,10]**

- 使用循环来追加数组。

- 声明一个空数组 arr。
- 循环中的计数器 i 可以作为数组元素存入。
- 由于数组的索引号是从0开始的， 因此计数器从 0 开始更合适，存入的数组元素要+1。

```js
var arr = [];
for (var i = 0; i < 10; i++){
    arr[i] = i + 1;
}
console.log(arr);
```

**2.将数组 [2, 0, 6, 1, 77, 0, 52, 0, 25, 7] 中大于等于 10 的元素选出来，放入新数组**

- ①声明一个新的数组用于存放新数据。
- ②遍历原来的数组，找出大于等于 10 的元素。
- ③依次追加给新数组 newArr。

实现代码1：

```js
var arr = [2, 0, 6, 1, 77, 0, 52, 0, 25, 7];
var newArr = [];
// 定义一个变量 用来计算 新数组的索引号
var j = 0;
for (var i = 0; i < arr.length; i++) {
    if (arr[i] >= 10) {
        // 给新数组
        newArr[j] = arr[i];
        // 索引号 不断自加
        j++;
    }
}
```

实现代码2：

```js
var arr = [2, 0, 6, 1, 77, 0, 52, 0, 25, 7];
var newArr = [];
for (var i = 0; i < arr.length; i++) {
    if (arr[i] >= 10) {
        // 给新数组
        newArr[newArr.length] = arr[i];
    }
}
console.log(newArr);
```

## 5.8、删除指定数组元素🔥

**将数组[2, 0, 6, 1, 77, 0, 52, 0, 25, 7]中的 0 去掉后，形成一个不包含 0 的新数组。**

```js
var arr = [2, 0, 6, 1, 77, 0, 52, 0, 25, 7];
var newArr = [];   // 空数组的默认的长度为 0 
// 定义一个变量 i 用来计算新数组的索引号
for (var i = 0; i < arr.length; i++) {
    // 找出大于 10 的数
    if (arr[i] != 0) {
        // 给新数组
        // 每次存入一个值，newArr长度都会 +1  
        newArr[newArr.length] = arr[i];
    }
}
console.log(newArr);
```

## 5.9、翻转数组🔥

**将数组 [‘red’, ‘green’, ‘blue’, ‘pink’, ‘purple’] 的内容反过来存放**

```js
// 把旧数组索引号的第4个取过来(arr.length - 1),给新数组索引号第0个元素(newArr.length)

var arr = ['red','green','blue','pink','purple'];
var newArr = [];
for (var i = arr.length -1; i>=0; i--){
    newArr[newArr.length] = arr[i];
}
console.log(newArr);
```

## 5.10、数组排序🔥

冒泡排序

将数组 [5, 4, 3, 2, 1]中的元素按照从小到大的顺序排序，输出： 1，2，3，4，5

```js
var arr = [5,4,3,2,1];
for (var i = 0; i < arr.length-1; i++){ //外层循环管趟数，5个数共交换4躺
    for (var j = 0; j <= arr.length - i - 1; j++){
        //里层循环管每一趟交换的次数
        //前一个和后面一个数组元素相比较
        if(arr[j] > arr[j+1]){
            var temp = arr[j];
            arr[j] = arr[j+1];
            arr[j+1] = temp;
        }  
    }
}
console.log(arr);
```

# 6、函数🔥

函数：就是封装了一段**可被重复调用执行的代码块**。通过此代码块可以实现大量代码的重复使用。

## 6.1、函数的使用🔥

函数在使用时分为两步：**声明函数**和**调用函数**

### ①声明函数🔥

```javascript
//声明函数
function 函数名(){
     //函数体代码
}
```

- function 是声明函数的关键字,**必须小写**
- 由于函数一般是为了实现某个功能才定义的， 所以通常我们将函数名命名为动词，比如 getSum

### ②调用函数🔥

```javascript
//调用函数
函数名(); //通过调用函数名来执行函数体代码
```

- 调用的时候**千万不要忘记添加小括号**
- 口诀：函数不调用，自己不执行

**注意**：声明函数本身并不会执行代码，只有调用函数时才会执行函数体代码。

## 6.2、函数的封装

- 函数的封装是把一个或者多个功能通过**函数的方式**封装起来，对外只提供一个简单的函数接口

## 6.3、函数的参数🔥

### 6.3.1、形参和实参🔥

**在声明函数时**，可以在函数名称后面的小括号中添加一些参数，这些参数被称为**形参**，而在**调用该函数**时，同样也需要传递相应的参数，这些参数被称为**实参**。

| 参数 | 说明                                                         |
| ---- | ------------------------------------------------------------ |
| 形参 | 形式上的参数 **函数定义**的时候 传递的参数 当前并不知道是什么 |
| 实参 | 实际上的参数 **函数调用**的时候 传递的参数 实参是传递给形参的 |

**参数的作用** : 在**函数内部**某些值不能固定，我们可以通过参数在**调用函数时传递不同的值**进去

```javascript
// 带参数的函数声明
function 函数名(形参1, 形参2 , 形参3...) { // 可以定义任意多的参数，用逗号分隔
  // 函数体
}

// 带参数的函数调用
函数名(实参1, 实参2, 实参3...); 
```

例如：利用函数求任意两个数的和

```javascript
// 声明函数
function getSum(num1,num2){
    console.log(num1+num2)
}

// 调用函数
getSum(1,3) //4
getSum(6，5) //11
```

- 函数调用的时候实参值是传递给形参的
- 形参简单理解为:**不用声明的变量**
- 实参和形参的多个参数之间用`逗号(,)`分隔，

### 6.3.2、形参和实参个数不匹配🔥

| 参数个数             | 说明                               |
| -------------------- | ---------------------------------- |
| 实参个数等于形参个数 | 输出正确结果                       |
| 实参个数多于形参个数 | 只取到形参的个数                   |
| 实参个数小于形参个数 | 多的形参定义为undefined，结果为NaN |

```javascript
function sum(num1, num2) {
    console.log(num1 + num2);
}
sum(100, 200);             // 300，形参和实参个数相等，输出正确结果

sum(100, 400, 500, 700);   // 500，实参个数多于形参，只取到形参的个数

sum(200);
```

**注意：在JavaScript中，形参的默认值是undefined**

### 6.3.3、小结🔥

- 函数可以带参数也可以不带参数
- 声明函数的时候，函数名括号里面的是形参，形参的默认值为 undefined
- 调用函数的时候，函数名括号里面的是实参
- 多个参数中间用逗号分隔
- 形参的个数可以和实参个数不匹配，但是结果不可预计，我们尽量要匹配

## 6.4、函数的返回值🔥

### 6.4.1、return语句🔥

有的时候，我们会希望函数将值返回给调用者，此时通过使用 return 语句就可以实现。

return 语句的语法格式如下：

```javascript
// 声明函数
function 函数名（）{
    ...
    return  需要返回的值;
}
// 调用函数
函数名();    // 此时调用函数就可以得到函数体内return 后面的值
```

- 在使用 return 语句时，函数会停止执行，并返回指定的值
- 如果函数没有 return ，返回的值是 undefined

```javascript
// 声明函数
function sum(){
    ...
    return  666;
}
// 调用函数
sum();      // 此时 sum 的值就等于666，因为 return 语句会把自身后面的值返回给调用者 
```

### 6.4.2、return 终止函数🔥

return 语句之后的代码不被执行

```javascript
function add(num1，num2){
    //函数体
    return num1 + num2; // 注意：return 后的代码不执行
    alert('我不会被执行，因为前面有 return');
}
var resNum = add(21,6); // 调用函数，传入两个实参，并通过 resNum 接收函数返回值
alert(resNum);          // 27
```

### 6.4.3、return 的返回值🔥

return **只能返回一个值**。如果用逗号隔开多个值，**以最后一个为准**

```javascript
function add(num1，num2){
    //函数体
    return num1,num2;
}
var resNum = add(21,6); // 调用函数，传入两个实参，并通过 resNum 接收函数返回值
alert(resNum);          // 6
```

### 6.4.4、小结🔥

函数都是有返回值的

1. 如果有 return ，则返回 return 后面的值
2. 如果没有 return，则返回 undefined

### 6.4.5、区别🔥

break、continue、return 的区别

- `break` ： 结束当前循环体(如 for、while)
- `continue` ：跳出本次循环，继续执行下次循环(如for、while)
- `return` ：不仅可以退出循环，还能够返回 return 语句中的值，同时还可以结束当前的函数体内的代码

### 6.4.6、练习

**1.利用函数求任意两个数的最大值**

```javascript
function getMax(num1, num2) {
    return num1 > num2 ? num1 : num2;
}
console.log(getMax(1, 2));
console.log(getMax(11, 2));
```

**2.求数组 [5,2,99,101,67,77] 中的最大数值**

```javascript
//定义一个获取数组中最大数的函数
function getMaxFromArr(numArray){
    var maxNum = numArray[0];
    for(var i = 0; i < numArray.length;i++){
        if(numArray[i]>maxNum){
            maxNum = numArray[i];
        }
    }
    return maxNum;
}
var arrNum = [5,2,99,101,67,77];
var maxN = getMaxFromArr(arrNum);  //这个实参是个数组
alert('最大值为' + maxN);
```

**3.创建一个函数，实现两个数之间的加减乘除运算，并将结果返回**

```javascript
var a = parseFloat(prompt('请输入第一个数'));
var b = parseFloat(prompt('请输入第二个数'));

function count(a,b){
    var arr = [a + b, a - b, a * b, a / b];
    return arr;
}
var result = count(a,b);
console.log(result)
```

## 6.5、arguments的使用🔥

当我们不确定有多少个参数传递的时候，可以用 arguments 来获取。在 JavaScript 中，arguments 实际上它是当前函数的一个内置对象。所有函数都内置了一个 arguments 对象，arguments 对象中存储了传递的所有实参。

- **arguments**存放的是传递过来的实参
- **arguments展示形式是一个伪数组，因此可以进行遍历。伪数组具有以下特点**

1. 具有 length 属性
2. 按索引方式储存数据
3. 不具有数组的 push , pop 等方法

```javascript
// 函数声明
function fn() {
    console.log(arguments);  //里面存储了所有传递过来的实参
    console.log(arrguments.length); // 3
    console.log(arrguments[2]); // 3
}

// 函数调用
fn(1,2,3);
```

例如：利用函数求任意个数的最大值

```javascript
 function maxValue() {
    var max = arguments[0];
    for (var i = 0; i < arguments.length; i++) {
        if (max < arguments[i]) {
            max = arguments[i];
        }
    }
    return max;
}
console.log(maxValue(2, 4, 5, 9)); // 9
console.log(maxValue(12, 4, 9)); // 12
```

## 6.6、函数练习🔥

**1.利用函数封装方式，翻转任意一个数组**

```javascript
function reverse(arr) {
    var newArr = [];
    for (var i = arr.length - 1; i >= 0; i--) {
        newArr[newArr.length] = arr[i];
    }
    return newArr;
}
var arr1 = reverse([1, 3, 4, 6, 9]);
console.log(arr1);
```

**2.利用函数封装方式，对数组排序 – 冒泡排序**

```javascript
function sort(arr) {
    for (var i = 0; i < arr.length - 1; i++) {
        for (var j = 0; j < arr.length - i - 1; j++) {
            if (arr[j] > arr[j+1]) { 
	            var temp = arr[j];
	            arr[j] = arr[j + 1]; 
	            arr[j + 1] = temp;
            }
        }
    }
    return arr;
}
```

**3.输入一个年份，判断是否是闰年（闰年：能被4整除并且不能被100整数，或者能被400整除）**

```javascript
function isRun(year) {
     var flag = false;
     if (year % 4 === 0 && year % 100 !== 0 || year % 400 === 0) {
        flag = true;
     }
    return flag;
}
console.log(isRun(2010));
console.log(isRun(2012));
```

**4.用户输入年份，输出当前年份2月份的天数，如果是闰年，则2月份是 29天， 如果是平年，则2月份是 28天**

```javascript
function backDay() {
    var year = prompt('请您输入年份:');
    if (isRun(year)) { //调用函数需要加小括号
        alert('你输入的' + year + '是闰年，2月份有29天');
    } else {
        alert('您输入的' + year + '不是闰年，2月份有28天');
    }
}
backDay();
//判断是否是闰年的函数
function isRun(year) {
    var flag = false;
    if (year % 4 === 0 && year % 100 !== 0 || year % 400 === 0) {
        flag = true;
    }
    return flag;
}
```

## 6.7、函数的两种声明方式🔥

### 6.7.1、自定义函数方式(命名函数)🔥

利用函数关键字 function 自定义函数方式。

```javascript
// 声明定义方式
function fn() {...}

// 调用  
fn(); 
```

1. **因为有名字，所以也被称为命名函数**
2. **调用函数的代码既可以放到声明函数的前面，也可以放在声明函数的后面**

### 6.7.2、函数表达式方式(匿名函数)🔥

利用函数表达式方式的写法如下：

```javascript
// 这是函数表达式写法，匿名函数后面跟分号结束
var fn = function(){...};

// 调用的方式，函数调用必须写到函数体下面
fn();
```

- 因为函数没有名字，所以也称为**匿名函数**
- 这个fn 里面存储的是一个函数
- **函数调用的代码必须写到函数体后面**

# 7、作用域🔥

通常来说，一段程序代码中所用到的名字并不总是有效和可用的，而限定这个名字的**可用性的代码范围**就是这个名字的**作用域**。作用域的使用提高了程序逻辑的局部性，增强了程序的可靠性，减少了名字冲突。

JavaScript (ES6前) 中的作用域有两种：

- 全局作用域
- 局部作用域(函数作用域)

## 7.1、全局作用域🔥

作用于所有代码执行的环境(整个 script 标签内部)或者一个独立的 js 文件

## 7.2、局部（函数）作用域🔥

作用于函数内的代码环境，就是局部作用域。 因为跟函数有关系，所以也称为函数作用域

## 7.3、JS 没有块级作用域🔥

- 块作用域由 `{}` 包括
- 在其他编程语言中（如 java、c#等），在 if 语句、循环语句中创建的变量，仅仅只能在本 if 语句、本循环语句中使用，如下面的Java代码：

```javascript
if(true){
    int num = 123;
    System.out.println(num);	// 123
}
System.out.println(num);		// 报错
```

JS 中没有块级作用域(在ES6之前)

```javascript
if(true){
    int num = 123;
    System.out.println(num);	// 123
}
System.out.println(num);		// 123
```

# 8、变量的作用域🔥

在JavaScript中，根据作用域的不同，变量可以分为两种：

- 全局变量
- 局部变量

## 8.1、全局变量🔥

在全局作用域下声明的变量叫做全局变量（**在函数外部定义的变量**）

- 全局变量在代码的任何位置都可以使用
- 在全局作用域下 var 声明的变量 是全局变量
- 特殊情况下，在函数内不使用 var 声明的变量也是全局变量（不建议使用）

## 8.2、局部变量🔥

在局部作用域下声明的变量叫做局部变量（**在函数内部定义的变量**）

- 局部变量只能在该函数内部使用
- 在函数内部 var 声明的变量是局部变量
- 函数的**形参**实际上就是**局部变量**

## 8.3、区别🔥

- 全局变量：在任何一个地方都可以使用，只有在浏览器关闭时才会被销毁，因此比较占内存
- 局部变量：只在函数内部使用，当其所在的代码块被执行时，会被初始化；当代码块运行结束后，就会被销毁，因此更节省内存空间

# 9、作用域链🔥

1. 只要是代码，就至少有一个作用域
2. 写在函数内部的叫局部作用域
3. 如果函数中还有函数，那么在这个作用域中就又可以诞生一个作用域
4. 根据在内部函数可以访问外部函数变量的这种机制，用链式查找决定哪些数据能被内部函数访问，就称作作用域链

```javascript
// 作用域链: 内部函数访问外部函数的变量，采取的是链式查找的方式来决定取哪个值，这种结构我们称为作用域链表

var num = 10;
funtion fn() { //外部函数
    var num = 20;
    
    function fun() { //内部函数
        console.log(num);  // 20 ,一级一级访问
    }
}
```

- 作用域链：采取**就近原则**的方式来查找变量最终的值。

# 10、预解析🔥

首先来看几段代码和结果：

```javascript
console.log(num);  // 结果是多少？
//会报错 num is undefined
```

```javascript
console.log(num);  // 结果是多少？
var num = 10;   
// undefined
```

```javascript
// 命名函数(自定义函数方式):若我们把函数调用放在函数声明上面
fn();				//11
function fn() {
    console.log('11');
}
```

```javascript
// 匿名函数(函数表达式方式):若我们把函数调用放在函数声明上面
fn();
var  fn = function() {
    console.log('22'); // 报错
}


//相当于执行了以下代码
var fn;
fn();      //fn没赋值，没这个，报错
var  fn = function() {
    console.log('22'); //报错
}
```

JavaScript 代码是由浏览器中的 JavaScript 解析器来执行的。JavaScript 解析器在运行 JavaScript 代码的时候分为两步：**预解析和代码执行。**

- **预解析**：js引擎会把js里面所有的 **var** 还有 **function** 提升到当前作用域的最前面
- **代码执行**：从上到下执行JS语句

预解析只会发生在通过 var 定义的变量和 function 上。学习预解析能够让我们知道**为什么在变量声明之前访问变量的值是 undefined**，**为什么在函数声明之前就可以调用函数**

## 10.1、变量预解析(变量提升)🔥

变量预解析也叫做变量提升、函数提升

变量提升: 变量的声明会被提升到**当前作用域**的最上面，变量的赋值不会提升

```javascript
console.log(num);  // 结果是多少？
var num = 10;   
// undefined



//相当于执行了以下代码
var num;		// 变量声明提升到当前作用域最上面
console.log(num);
num = 10;		// 变量的赋值不会提升
```

## 10.2、函数预解析(函数提升)🔥

函数提升： 函数的声明会被提升到**当前作用域**的最上面，但是不会调用函数。

```javascript
fn();				//11
function fn() {
    console.log('11');
}
```

## 10.3、解决函数表达式声明调用问题🔥

对于函数表达式声明调用需要记住：**函数表达式调用必须写在函数声明的下面**

```javascript
// 匿名函数(函数表达式方式):若我们把函数调用放在函数声明上面
fn();
var  fn = function() {
    console.log('22'); // 报错
}


//相当于执行了以下代码
var fn;
fn();      //fn没赋值，没这个，报错
var  fn = function() {
    console.log('22'); //报错
}
```

## 10.4、预解析练习🔥

预解析部分十分重要，可以通过下面4个练习来理解。

[Pink老师的视频讲解预解析](https://www.bilibili.com/video/BV1Sy4y1C7ha?p=143)

```javascript
// 练习1
var num = 10;
fun();
function fun() {
    console.log(num);	//undefined
    var num = 20;
}
// 最终结果是 undefined
```

上述代码相当于执行了以下操作

```javascript
var num;
function fun() {
    var num;
    console.log(num);
    num = 20;
}
num = 10;
fun();
```

```javascript
// 练习2
var num = 10;
function fn(){
    console.log(num);		//undefined
    var num = 20;
    console.log(num);		//20
}
fn();
// 最终结果是 undefined 20
```

上述代码相当于执行了以下操作

```javascript
var num;
function fn(){
    var num;
    console.log(num);
    num = 20;
    console.log(num);
}
num = 10;
fn();
```

```javascript
// 练习3
var a = 18;
f1();

function f1() {
    var b = 9;
    console.log(a);
    console.log(b);
    var a = '123';
}
```

上述代码相当于执行了以下操作

```javascript
var a;
function f1() {
    var b;
    var a
    b = 9;
    console.log(a);	//undefined
    console.log(b);	//9
    a = '123';
}
a = 18;
f1();
```

```javascript
// 练习4
f1();
console.log(c);
console.log(b);
console.log(a);
function f1() {
    var a = b = c = 9;
    // 相当于 var a = 9; b = 9;c = 9;  b和c的前面没有var声明,当全局变量看
    // 集体声明 var a = 9,b = 9,c = 9;
    console.log(a);
    console.log(b);
    console.log(c);
}
```

上述代码相当于执行了以下操作

```javascript
function f1() {
    var a;
    a = b = c = 9;
    console.log(a);	//9
    console.log(b);	//9
    console.log(c);	//9
}
f1();
console.log(c);	//9
console.log(b);	//9
console.log(a);	//报错 a是局部变量
```


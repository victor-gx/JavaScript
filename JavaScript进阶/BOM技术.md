# 1、BOM概述

- BOM = Browser Object Model 浏览器对象模型
- 它提供了独立于内容而与浏览器窗口进行交互的对象，其核心对象是 window
- BOM 由一系列相关的对象构成，并且每个对象都提供了很多方法与属性
- BOM 缺乏标准，JavaScript 语法的标准化组织是 ECMA, DOM 的标准化组织是 W3C, BOM最初是Netscape 浏览器标准的一部分

| DOM                                | BOM                                              |
| ---------------------------------- | ------------------------------------------------ |
| 文档对象模型                       | 浏览器对象模型                                   |
| DOM 就是把 文档 当作一个对象来看待 | 把 浏览器当作一个对象来看待                      |
| DOM 的顶级对象是 document          | BOM 的顶级对象是 window                          |
| DOM 主要学习的是操作页面元素       | BOM 学习的是浏览器窗口交互的一些对象             |
| DOM 是 W3C 标准规范                | BOM 是浏览器厂商在各自浏览器上定义的，兼容性较差 |

## 1.1、BOM的构成

![image-20221031214501899](https://victor-gx.oss-cn-beijing.aliyuncs.com/img/2022/JavaScript/202210312145950.png)

- BOM 比 DOM 更大。它包含 DOM。
- window 对象是浏览器的顶级对象，它具有双重角色
- 它是 JS 访问浏览器窗口的一个接口
- 它是一个全局对象。定义在全局作用域中的变量、函数都会变成 window 对象的属性和方法
- 在调用的时候可以省略 window，前面学习的对话框都属于 window 对象方法，如 `alert()、prompt()`等。
- **注意**：window下的一个特殊属性 window.name

```javascript
// 定义在全局作用域中的变量会变成window对象的属性
var num = 10;
console.log(window.num);
// 10

// 定义在全局作用域中的函数会变成window对象的方法
function fn() {
    console.log(11);
}
console.fn();
// 11

var name = 10;  //不要用这个name变量,window下有一个特殊属性window.name
console.log(window.num);
```


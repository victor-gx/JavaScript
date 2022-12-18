# ECMASript 相关介绍

##  什么是ECMA

 ECMA（European Computer Manufacturers Association）中文名称为欧洲计算机制  造商协会，这个组织的目标是评估、开发和认可电信和计算机标准。1994 年后该  组织改名为 Ecma 国际。  

##  什么是 ECMAScript

ECMAScript 是由 Ecma 国际通过 ECMA-262 标准化的脚本程序设计语言

## 什么是 ECMA-262

 Ecma 国际制定了许多标准，而 ECMA-262 只是其中的一个，所有标准列表查看    http://www.ecma-international.org/publications/standards/Standard.htm  

## ECMA-262 历史

 ECMA-262（ECMAScript）历史版本查看网址    http://www.ecma-international.org/publications/standards/Ecma-262-arch.htm  

## 谁在维护 ECMA-262

 TC39（Technical Committee 39）是推进 ECMAScript 发展的委员会。其会员都是  公司（其中主要是浏览器厂商，有苹果、谷歌、微软、因特尔等）。TC39 定期  召开会议，会议由会员公司的代表与特邀专家出席  

## 为什么要学习 **ES6**

- ES6 的版本变动内容最多，具有里程碑意义 
- ES6 加入许多新的语法特性，编程实现更简单、高效 
- ES6 是前端发展趋势，就业必备技能  

## **ES6** 兼容性

 http://kangax.github.io/compat-table/es6/[ ](http://kangax.github.io/compat-table/es6/)可查看兼容性  

# ECMASript 6 新特性

## let 关键字

 `let` 关键字用来声明变量，使用 `let` 声明的变量有几个特点

1. 不允许重复声明  
2. 块儿级作用域
3. 不存在变量提升
4. 不影响作用域链

```html
<body>
    <script>
        //声明变量
        let a;
        let b,c,d;
        let e = 100;
        let f = 521, g = 'iloveyou', h = [];

        //1. 变量不能重复声明
        // let star = '罗志祥';
        // let star = '小猪';

        //2. 块儿级作用域  全局, 函数, eval
        // if else while for 
        // {
        //     let girl = '周扬青';
        // }
        // console.log(girl);

        //3. 不存在变量提升
        // console.log(song);
        // let song = '恋爱达人';

        //4. 不影响作用域链
        {
            let school = '尚硅谷';
            function fn(){
                console.log(school);
            }
            fn();
        }

    </script>
</body>
```

 ==应用场景：以后声明变量使用 **let** 就对了==

```html
<body>
    <script>
        //获取div元素对象
        let items = document.getElementsByClassName('item');

        //遍历并绑定事件
        for(let i = 0;i<items.length;i++){
            items[i].onclick = function(){
                //修改当前元素的背景颜色
                // this.style.background = 'pink';
                items[i].style.background = 'pink';
            }
        }
        
    </script>
</body>
```

## const 关键字

  `const` 关键字用来声明常量，`const` 声明有以下特点

1. 声明必须赋初始值  
2. 标识符一般为大写  
3. 不允许重复声明  
4. 值不允许修改  
5. 块儿级作用域  

```html
<body>
    <script>
        //声明常量
        const SCHOOL = '尚硅谷';

        //1. 一定要赋初始值
        // const A;
        //2. 一般常量使用大写(潜规则)
        // const a = 100;
        //3. 常量的值不能修改
        // SCHOOL = 'ATGUIGU';
        //4. 块儿级作用域
        // {
        //     const PLAYER = 'UZI';
        // }
        // console.log(PLAYER);
        //5. 对于数组和对象的元素修改, 不算做对常量的修改, 不会报错
        const TEAM = ['UZI','MXLG','Ming','Letme'];
        // TEAM.push('Meiko'); 
    </script>
</body>
```

==注意**:** 对象属性修改和数组元素变化不会出发 **const** 错误==

==应用场景：声明对象类型使用 **const**，非对象类型声明选择 **let**==

## 变量的解构赋值

ES6 允许按照一定模式，从数组和对象中提取值，对变量进行赋值，这被称为解构赋值。

```html
<body>
    <script>
        //ES6 允许按照一定模式从数组和对象中提取值，对变量进行赋值，
        //这被称为解构赋值。
        //1. 数组的结构
        // const F4 = ['小沈阳','刘能','赵四','宋小宝'];
        // let [xiao, liu, zhao, song] = F4;
        // console.log(xiao);
        // console.log(liu);
        // console.log(zhao);
        // console.log(song);

        //2. 对象的解构
        // const zhao = {
        //     name: '赵本山',
        //     age: '不详',
        //     xiaopin: function(){
        //         console.log("我可以演小品");
        //     }
        // };

        // let {name, age, xiaopin} = zhao;
        // console.log(name);
        // console.log(age);
        // console.log(xiaopin);
        // xiaopin();

        let {xiaopin} = zhao;
        xiaopin();


    </script>
</body>
```

==注意：频繁使用对象方法、数组元素，就可以使用解构赋值形式==

## 模板字符串

模板字符串（template string）是增强版的字符串，用反引号(`)标识，特点

1. 字符串中可以出现换行符
2. 可以使用 `${xxx} `形式输出变量  

```html
<body>
    <script>
        // ES6 引入新的声明字符串的方式 `` '' "" 
        //1. 声明
        // let str = `我也是一个字符串哦!`;
        // console.log(str, typeof str);

        //2. 内容中可以直接出现换行符
        let str = `<ul>
                    <li>沈腾</li>
                    <li>玛丽</li>
                    <li>魏翔</li>
                    <li>艾伦</li>
                    </ul>`;
        //3. 变量拼接
        let lovest = '魏翔';
        let out = `${lovest}是我心目中最搞笑的演员!!`;
        console.log(out);

    </script>
</body>
```

## 简化对象写法

 ES6 允许在大括号里面，直接写入变量和函数，作为对象的属性和方法。这样的书写更加简洁。  

```html
<body>
    <script>
        //ES6 允许在大括号里面，直接写入变量和函数，作为对象的属性和方法。
        //这样的书写更加简洁
        let name = '尚硅谷';
        let change = function(){
            console.log('我们可以改变你!!');
        }

        const school = {
            name,
            change,
            improve(){
                console.log("我们可以提高你的技能");
            }
        }

        console.log(school);

    </script>
</body>
```

==注意：对象简写形式简化了代码，所以以后用简写就对了==  

## 箭头函数

  ES6 允许使用`=>`定义函数。  

  箭头函数的注意点:  

1. 如果形参只有一个，则小括号可以省略
2. 函数体如果只有一条语句，则花括号可以省略，函数的返回值为该条语句的执行结果  
3. 箭头函数 this 指向声明时所在作用域下 `this` 的值
4. 箭头函数不能作为构造函数实例化
5. 不能使用 `arguments ` 

```html
<body>
    <script>
        // ES6 允许使用「箭头」（=>）定义函数。
        //声明一个函数
        // let fn = function(){

        // }
        // let fn = (a,b) => {
        //     return a + b;
        // }
        //调用函数
        // let result = fn(1, 2);
        // console.log(result);


        //1. this 是静态的. this 始终指向函数声明时所在作用域下的 this 的值
        function getName(){
            console.log(this.name);
        }
        let getName2 = () => {
            console.log(this.name);
        }

        //设置 window 对象的 name 属性
        window.name = '尚硅谷';
        const school = {
            name: "ATGUIGU"
        }

        //直接调用
        // getName();
        // getName2();

        //call 方法调用
        // getName.call(school);
        // getName2.call(school);

        //2. 不能作为构造实例化对象
        // let Person = (name, age) => {
        //     this.name = name;
        //     this.age = age;
        // }
        // let me = new Person('xiao',30);
        // console.log(me);

        //3. 不能使用 arguments 变量
        // let fn = () => {
        //     console.log(arguments);
        // }
        // fn(1,2,3);

        //4. 箭头函数的简写
            //1) 省略小括号, 当形参有且只有一个的时候
            // let add = n => {
            //     return n + n;
            // }
            // console.log(add(9));
            //2) 省略花括号, 当代码体只有一条语句的时候, 此时 return 必须省略
            // 而且语句的执行结果就是函数的返回值
            let pow = n => n * n;
                
            console.log(pow(8));

    </script>
</body>
```

 ==注意：箭头函数不会更改 **this** 指向，用来指定回调函数会非常合适==  

```html
<body>
    <div id="ad"></div>
    <script>
        //需求-1  点击 div 2s 后颜色变成『粉色』
        //获取元素
        let ad = document.getElementById('ad');
        //绑定事件
        ad.addEventListener("click", function(){
            //保存 this 的值
            // let _this = this;
            //定时器
            setTimeout(() => {
                //修改背景颜色 this
                // console.log(this);
                // _this.style.background = 'pink';
                this.style.background = 'pink';
            }, 2000);
        });

        //需求-2  从数组中返回偶数的元素
        const arr = [1,6,9,10,100,25];
        // const result = arr.filter(function(item){
        //     if(item % 2 === 0){
        //         return true;
        //     }else{
        //         return false;
        //     }
        // });
        
        const result = arr.filter(item => item % 2 === 0);

        console.log(result);

        // 箭头函数适合与 this 无关的回调. 定时器, 数组的方法回调
        // 箭头函数不适合与 this 有关的回调.  事件回调, 对象的方法

    </script>
</body>

```

## 参数默认值

```html
<body>
    <script>
        //ES6 允许给函数参数赋值初始值
        //1. 形参初始值 具有默认值的参数, 一般位置要靠后(潜规则)
        // function add(a,c=10,b) {
        //     return a + b + c;
        // }
        // let result = add(1,2);
        // console.log(result);

        //2. 与解构赋值结合
        function connect({host="127.0.0.1", username,password, port}){
            console.log(host)
            console.log(username)
            console.log(password)
            console.log(port)
        }
        connect({
            host: 'atguigu.com',
            username: 'root',
            password: 'root',
            port: 3306
        })
    </script>
</body>
```

## rest 参数

ES6 引入 `rest` 参数，用于获取函数的实参，用来代替 `arguments`  

```html
<body>
    <script>
        // ES6 引入 rest 参数，用于获取函数的实参，用来代替 arguments
        // ES5 获取实参的方式
        // function date(){
        //     console.log(arguments);
        // }
        // date('白芷','阿娇','思慧');

        // rest 参数
        // function date(...args){
        //     console.log(args);// filter some every map 
        // }
        // date('阿娇','柏芝','思慧');

        // rest 参数必须要放到参数最后
        // function fn(a,b,...args){
        //     console.log(a);
        //     console.log(b);
        //     console.log(args);
        // }
        // fn(1,2,3,4,5,6);

    </script>
</body>
```

==注意：**rest** 参数非常适合不定个数参数函数的场景==  

## spread 扩展运算符  

扩展运算符（spread）也是三个点`...`。它好比`rest` 参数的逆运算，将一个数组转为用逗号分隔的参数序列，对数组进行解包。  

```html
<body>
    <script>
        // ... 扩展运算符能将『数组』转换为逗号分隔的参数序列
        //声明一个数组 ...
        const tfboys = ['易烊千玺','王源','王俊凯'];
        // => '易烊千玺','王源','王俊凯'

        // 声明一个函数
        function chunwan(){
            console.log(arguments);
        }

        chunwan(...tfboys);// chunwan('易烊千玺','王源','王俊凯')

        

    </script>
</body>
```

应用

```html
<body>
    <div></div>
    <div></div>
    <div></div>
    <script>
        //1. 数组的合并 情圣  误杀  唐探
        // const kuaizi = ['王太利','肖央'];
        // const fenghuang = ['曾毅','玲花'];
        // // const zuixuanxiaopingguo = kuaizi.concat(fenghuang);
        // const zuixuanxiaopingguo = [...kuaizi, ...fenghuang];
        // console.log(zuixuanxiaopingguo);

        //2. 数组的克隆
        // const sanzhihua = ['E','G','M'];
        // const sanyecao = [...sanzhihua];//  ['E','G','M']
        // console.log(sanyecao);

        //3. 将伪数组转为真正的数组
        const divs = document.querySelectorAll('div');
        const divArr = [...divs];
        console.log(divArr);// arguments 
    </script>
</body>
```


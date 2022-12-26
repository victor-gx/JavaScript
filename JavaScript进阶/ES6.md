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

## Symbol

### Symbol 基本使用

ES6 引入了一种新的原始数据类型 Symbol，表示独一无二的值。它是JavaScript 语言的第七种数据类型，是一种类似于字符串的数据类型。

Symbol 特点  

1. Symbol 的值是唯一的，用来解决命名冲突的问题
2. Symbol 值不能与其他数据进行运算  
3. Symbol 定 义 的 对 象 属 性 不 能 使 用 `for…in` 循 环 遍 历 ， 但 是 可 以 使 用  `Reflect.ownKeys` 来获取对象的所有键名  

```html
<body>
    <script>
        //创建Symbol
        let s = Symbol();
        // console.log(s, typeof s);
        let s2 = Symbol('尚硅谷');
        let s3 = Symbol('尚硅谷');
        //Symbol.for 创建
        let s4 = Symbol.for('尚硅谷');
        let s5 = Symbol.for('尚硅谷');

        //不能与其他数据进行运算
        //    let result = s + 100;
        //    let result = s > 100;
        //    let result = s + s;

        // USONB  you are so niubility 
        // u  undefined
        // s  string  symbol
        // o  object
        // n  null number
        // b  boolean

    </script>
</body>
```

使用场景：

```html
<body>
    <script>
        //向对象中添加方法 up down
        let game = {
            name:'俄罗斯方块',
            up: function(){},
            down: function(){}
        };
        
        //声明一个对象
        // let methods = {
        //     up: Symbol(),
        //     down: Symbol()
        // };

        // game[methods.up] = function(){
        //     console.log("我可以改变形状");
        // }

        // game[methods.down] = function(){
        //     console.log("我可以快速下降!!");
        // }

        // console.log(game);

        //
        let youxi = {
            name:"狼人杀",
            [Symbol('say')]: function(){
                console.log("我可以发言")
            },
            [Symbol('zibao')]: function(){
                console.log('我可以自爆');
            }
        }

        console.log(youxi)

        
    </script>
</body>
```

==注**:**  遇到唯一性的场景时要想到 **Symbol**==  

### Symbol 内置值

除了定义自己使用的 Symbol 值以外，ES6 还提供了 11 个内置的 Symbol 值，  指向语言内部使用的方法。可以称这些方法为魔术方法，因为它们会在特定的场景下自动执行。 

| Symbol 值                   | 功能                                                         |
| --------------------------- | ------------------------------------------------------------ |
| `Symbol.hasInstance`        | 当其他对象使用 `instanceof` 运算符，判断是否为该对象的实例时，会调用这个方法 |
| `Symbol.isConcatSpreadable` | 对象的 `Symbol.isConcatSpreadable` 属性等于的是一个布尔值，表示该对象用于` Array.prototype.concat()`时，是否可以展开。 |
| `Symbol.species`            | 创建衍生对象时，会使用该属性                                 |
| `Symbol.match`              | 当执行 `str.match(myObject)` 时，如果该属性存在，会调用它，返回该方法的返回值。 |
| `Symbol.replace`            | 当该对象被 `str.replace(myObject)`方法调用时，会返回该方法的返回值。 |
| `Symbol.search`             | 当该对象被 `str. search (myObject)`方法调用时，会返回该方法的返回值。 |
| `Symbol.split`              | 当该对象被 `str. split (myObject)`方法调用时，会返回该方法的返回值。 |
| `Symbol.iterator`           | 对象进行 `for...of` 循环时，会调用 `Symbol.iterator` 方法，返回该对象的默认遍历器 |
| `Symbol.toPrimitive`        | 该对象被转为原始类型的值时，会调用这个方法，返回该对象对应的原始类型值。 |
| `Symbol. toStringTag  `     | 在该对象上面调用 `toString` 方法时，返回该方法的返回值       |
| `Symbol. unscopables  `     | 该对象指定了使用` with` 关键字时，哪些属性会被 `with`环境排除。 |

```html
<body>
    <script>
        // class Person{
        //     static [Symbol.hasInstance](param){
        //         console.log(param);
        //         console.log("我被用来检测类型了");
        //         return false;
        //     }
        // }

        // let o = {};

        // console.log(o instanceof Person);

        // const arr = [1,2,3];
        // const arr2 = [4,5,6];
        // arr2[Symbol.isConcatSpreadable] = false;
        // console.log(arr.concat(arr2));
    </script>
</body>
```

## 迭代器

迭代器（Iterator）就是一种机制。它是一种接口，为各种不同的数据结构提  供统一的访问机制。任何数据结构只要部署 Iterator 接口，就可以完成遍历操作。  

1. ES6 创造了一种新的遍历命令 for...of 循环，Iterator 接口主要供 for...of 消费  
2. 原生具备 iterator 接口的数据(可用  for of 遍历)  
   - Array  
   - Arguments  
   - Set  
   - Map  
   - String  
   - TypedArray  
   - NodeList  

3. 工作原理  
   - 创建一个指针对象，指向当前数据结构的起始位置
   - 第一次调用对象的 next 方法，指针自动指向数据结构的第一个成员
   - 接下来不断调用 next 方法，指针一直往后移动，直到指向最后一个成员
   - 每调用 next 方法返回一个包含 value 和 done 属性的对象  

```html
<body>
    <script>
        //声明一个数组
        const xiyou = ['唐僧','孙悟空','猪八戒','沙僧'];

        //使用 for...of 遍历数组
        // for(let v of xiyou){
        //     console.log(v);
        // }

        let iterator = xiyou[Symbol.iterator]();

        //调用对象的next方法
        console.log(iterator.next());
        console.log(iterator.next());
        console.log(iterator.next());
        console.log(iterator.next());
        console.log(iterator.next());
    </script>
</body>
```

==注:  需要自定义遍历数据的时候，要想到迭代器。==

```html
<body>
    <script>
        //声明一个对象
        const banji = {
            name: "终极一班",
            stus: [
                'xiaoming',
                'xiaoning',
                'xiaotian',
                'knight'
            ],
            [Symbol.iterator]() {
                //索引变量
                let index = 0;
                //
                let _this = this;
                return {
                    next: function () {
                        if (index < _this.stus.length) {
                            const result = { value: _this.stus[index], done: false };
                            //下标自增
                            index++;
                            //返回结果
                            return result;
                        }else{
                            return {value: undefined, done: true};
                        }
                    }
                };
            }
        }

        //遍历这个对象 
        for (let v of banji) {
            console.log(v);
        }
    </script>
</body>
```

## 生成器

生成器函数是 ES6 提供的一种异步编程解决方案，语法行为与传统函数完全不同  

```html
<body>
    <script>    
        //生成器其实就是一个特殊的函数
        //异步编程  纯回调函数  node fs  ajax mongodb
        //函数代码的分隔符
        function * gen(){
            // console.log(111);
            yield '一只没有耳朵';
            // console.log(222);
            yield '一只没有尾部';
            // console.log(333);
            yield '真奇怪';
            // console.log(444);
        }

        let iterator = gen();
        console.log(iterator.next());
        console.log(iterator.next());
        console.log(iterator.next());
        console.log(iterator.next());

        //遍历
        // for(let v of gen()){
        //     console.log(v);
        // }

    </script>
</body>
```

代码说明：  

1. `*`的位置没有限制  
2. 生成器函数返回的结果是迭代器对象，调用迭代器对象的 `next` 方法可以得到  `yield` 语句后的值  
3. `yield` 相当于函数的暂停标记，也可以认为是函数的分隔符，每调用一次 `next`  方法，执行一段代码  
4. `next` 方法可以传递实参，作为 `yield` 语句的返回值

**生成器函数的参数传递**

```html
<body>
    <script>
        function * gen(arg){
            console.log(arg);
            let one = yield 111;
            console.log(one);
            let two = yield 222;
            console.log(two);
            let three = yield 333;
            console.log(three);
        }

        //执行获取迭代器对象
        let iterator = gen('AAA');
        console.log(iterator.next());
        //next方法可以传入实参
        console.log(iterator.next('BBB'));
        console.log(iterator.next('CCC'));
        console.log(iterator.next('DDD'));
        
    </script>
</body>
```

实例

```html
<body>
    <script>
        // 异步编程  文件操作 网络操作(ajax, request) 数据库操作
        // 1s 后控制台输出 111  2s后输出 222  3s后输出 333 
        // 回调地狱
        // setTimeout(() => {
        //     console.log(111);
        //     setTimeout(() => {
        //         console.log(222);
        //         setTimeout(() => {
        //             console.log(333);
        //         }, 3000);
        //     }, 2000);
        // }, 1000);

        function one(){
            setTimeout(()=>{
                console.log(111);
                iterator.next();
            },1000)
        }

        function two(){
            setTimeout(()=>{
                console.log(222);
                iterator.next();
            },2000)
        }

        function three(){
            setTimeout(()=>{
                console.log(333);
                iterator.next();
            },3000)
        }

        function * gen(){
            yield one();
            yield two();
            yield three();
        }

        //调用生成器函数
        let iterator = gen();
        iterator.next();

    </script>
</body>
```

```html
<body>
    <script>
        //模拟获取  用户数据  订单数据  商品数据 
        function getUsers(){
            setTimeout(()=>{
                let data = '用户数据';
                //调用 next 方法, 并且将数据传入
                iterator.next(data);
            }, 1000);
        }

        function getOrders(){
            setTimeout(()=>{
                let data = '订单数据';
                iterator.next(data);
            }, 1000)
        }

        function getGoods(){
            setTimeout(()=>{
                let data = '商品数据';
                iterator.next(data);
            }, 1000)
        }

        function * gen(){
            let users = yield getUsers();
            let orders = yield getOrders();
            let goods = yield getGoods();
        }

        //调用生成器函数
        let iterator = gen();
        iterator.next();
    </script>
</body>
```

## Promise

Promise 是 ES6 引入的异步编程的新解决方案。语法上 Promise 是一个构造函数，  用来封装异步操作并可以获取其成功或失败的结果。

1. Promise 构造函数: `Promise (excutor) {}  `
2. `Promise.prototype.then` 方法 
3. `Promise.prototype.catch` 方法

### Promise基本语法

```html
<body>
    <script>
        //实例化 Promise 对象
        const p = new Promise(function(resolve, reject){
            setTimeout(function(){
                //
                // let data = '数据库中的用户数据';
                // resolve
                // resolve(data);

                let err = '数据读取失败';
                reject(err);
            }, 1000);
        });

        //调用 promise 对象的 then 方法
        p.then(function(value){
            console.log(value);
        }, function(reason){
            console.error(reason);
        })
    </script>
</body>
```

### Promise封装读取文件

```javascript
//1. 引入 fs 模块
const fs = require('fs');

//2. 调用方法读取文件
// fs.readFile('./resources/为学.md', (err, data)=>{
//     //如果失败, 则抛出错误
//     if(err) throw err;
//     //如果没有出错, 则输出内容
//     console.log(data.toString());
// });

//3. 使用 Promise 封装
const p = new Promise(function(resolve, reject){
    fs.readFile("./resources/为学.md", (err, data)=>{
        //判断如果失败
        if(err) reject(err);
        //如果成功
        resolve(data);
    });
});

p.then(function(value){
    console.log(value.toString());
}, function(reason){
    console.log("读取失败!!");
});

```

### Promise发送 AJAX 请求

```html
<body>
    <script>
        // 接口地址: https://api.apiopen.top/getJoke
        const p = new Promise((resolve, reject) => {
            //1. 创建对象
            const xhr = new XMLHttpRequest();

            //2. 初始化
            xhr.open("GET", "https://api.apiopen.top/getJoke");

            //3. 发送
            xhr.send();

            //4. 绑定事件, 处理响应结果
            xhr.onreadystatechange = function () {
                //判断
                if (xhr.readyState === 4) {
                    //判断响应状态码 200-299
                    if (xhr.status >= 200 && xhr.status < 300) {
                        //表示成功
                        resolve(xhr.response);
                    } else {
                        //如果失败
                        reject(xhr.status);
                    }
                }
            }
        })
        
        //指定回调
        p.then(function(value){
            console.log(value);
        }, function(reason){
            console.error(reason);
        });
    </script>
</body>
```

### Promise-then方法

```html
<body>
    <script>
        //创建 promise 对象
        const p = new Promise((resolve, reject)=>{
            setTimeout(()=>{
                resolve('用户数据');
                // reject('出错啦');
            }, 1000)
        });

        //调用 then 方法  then方法的返回结果是 Promise 对象, 对象状态由回调函数的执行结果决定
        //1. 如果回调函数中返回的结果是 非 promise 类型的属性, 状态为成功, 返回值为对象的成功的值

        // const result = p.then(value => {
        //     console.log(value);
        //     //1. 非 promise 类型的属性
        //     // return 'iloveyou';
        //     //2. 是 promise 对象
        //     // return new Promise((resolve, reject)=>{
        //     //     // resolve('ok');
        //     //     reject('error');
        //     // });
        //     //3. 抛出错误
        //     // throw new Error('出错啦!');
        //     throw '出错啦!';
        // }, reason=>{
        //     console.warn(reason);
        // });

        //链式调用
        p.then(value=>{

        }).then(value=>{

        });


    </script>
</body>
```

### Promise实践

读取多个文件

```javascript
//引入 fs 模块
const fs = require("fs");

// fs.readFile('./resources/为学.md', (err, data1)=>{
//     fs.readFile('./resources/插秧诗.md', (err, data2)=>{
//         fs.readFile('./resources/观书有感.md', (err, data3)=>{
//             let result = data1 + '\r\n' +data2  +'\r\n'+ data3;
//             console.log(result);
//         });
//     });
// });

//使用 promise 实现
const p = new Promise((resolve, reject) => {
    fs.readFile("./resources/为学.md", (err, data) => {
        resolve(data);
    });
});

p.then(value => {
    return new Promise((resolve, reject) => {
        fs.readFile("./resources/插秧诗.md", (err, data) => {
            resolve([value, data]);
        });
    });
}).then(value => {
    return new Promise((resolve, reject) => {
        fs.readFile("./resources/观书有感.md", (err, data) => {
            //压入
            value.push(data);
            resolve(value);
        });
    })
}).then(value => {
    console.log(value.join('\r\n'));
});
```

### catch方法

```html
<body>
    <script>
        const p = new Promise((resolve, reject)=>{
            setTimeout(()=>{
                //设置 p 对象的状态为失败, 并设置失败的值
                reject("出错啦!");
            }, 1000)
        });

        // p.then(function(value){}, function(reason){
        //     console.error(reason);
        // });

        p.catch(function(reason){
            console.warn(reason);
        });
    </script>
</body>
```

## Set

ES6 提供了新的数据结构 `set`（集合）。它类似于数组，但成员的值都是唯一的，集合实现了 `iterator` 接口，所以可以使用`扩展运算符`和`for…of…`进  行遍历，集合的属性和方法：  

1. `size`返回集合的元素个数  
2. `add`增加一个新元素，返回当前集合  
3. `delete` 删除元素，返回 `boolean` 值  
4. `has `检测集合中是否包含某个元素，返回 `boolean` 值
5. `clear`清空集合，返回 `undefined`  

## Map

ES6 提供了 `Map` 数据结构。它类似于对象，也是键值对的集合。但是“键”的范围不限于字符串，各种类型的值（包括对象）都可以当作键。Map 也实现了`iterator` 接口，所以可以使用`扩展运算符`和`for…of…`进行遍历。Map 的属性和方法：  

1. `size`返回`Map`的元素个数  
2. `add`增加一个新元素，返回当前`Map`  
3. `get` 返回键名对象的键值 
4. `has `检测`Map`中是否包含某个元素，返回 `boolean` 值
5. `clear`清空集合，返回 `undefined`  

## class 类

ES6 提供了更接近传统语言的写法，引入了 Class（类）这个概念，作为对象的模板。通过 `class` 关键字，可以定义类。基本上，ES6 的 `class` 可以看作只是一个语法糖，它的绝大部分功能，ES5 都可以做到，新的 `class` 写法只是让对象原型的写法更加清晰、更像面向对象编程的语法而已。  

知识点：

1. `class` 声明类  
2. `constructor` 定义构造函数初始化  
3. `extends` 继承父类  
4. `super` 调用父级构造方法  
5. `static` 定义静态方法和属性  
6. 父类方法可以重写

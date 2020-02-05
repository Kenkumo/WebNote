# JavaScript基础

## JavaScript组成

- ECMAScript：JavaScript语法
- DOM：页面文档对象模型
- BOM：浏览器对象模型

## JavaScript书写方式

### 行内式 

```html
<input type="button" value="点我试试" onclick="alert('Hello World')" />
```

### 内嵌式

```html
  <script>
      alert('Hello  World~!');
  </script>
```

### 外链式

```html
  <script src="my.js"></script>
```

## JavaScript注释

- 单行注释：//, ctrl+/
- 多行注释：/* */, alt+shift+a建议改为ctrl+shift+/

## JavaScript输入输出语句

| 方法             | 说明                           | 归属   |
| ---------------- | ------------------------------ | ------ |
| alert(msg)       | 浏览器弹出警示框               | 浏览器 |
| console.log(msg) | 浏览器控制台打印输出信息       | 浏览器 |
| prompt(info)     | 浏览器弹出输入框，用户可以输入 | 浏览器 |

- 注意：alert() 主要用来显示消息给用户，console.log() 用来给程序员自己看运行时的消息。

## 变量

```javascript
// 声明变量
var age;

// 赋值
age = 10;

// 变量的初始化
var age = 10;

// 更新变量
var age = 18;
age = 81;

// 同时声明多个变量
var age = 10, name = 'zs', sex = 2;
```

### 声明变量特殊情况

| 情况                           | 说明                    | 结果      |
| ------------------------------ | ----------------------- | --------- |
| var  age ; console.log (age);  | 只声明 不赋值           | undefined |
| console.log(age)               | 不声明 不赋值  直接使用 | 报错      |
| age   = 10; console.log (age); | 不声明   只赋值         | 10        |

## 数据类型

### 数据类型分类

- 简单数据类型：Number,String,Boolean,Undefined,Null
- 复杂数据类型：Object

### 数值型Number

可保存整数和小数（浮点数）

- 数字型进制：八进制（0），十六进制（0x）
- 数字型范围：
  - 最大值：Number.MAX_VALUE
  - 最小值：Number.MIN_VALUE
- 三个特殊值
  - Infinity：无穷大
  - -Infinity：无穷小
  - NaN：代表非数值
- isNaN(x)：判断一个变量是否为非数值的类型，返回true或false

### 字符串型String

- 字符串引号嵌套

```javascript
// 可以用''包含""
var strMsg = '我是"高富帅"啊';
// 也可以用""包含''
var strMsg2 = "我是'高富帅'啊";
```

- 字符串转义符

| 转义符 | 解释说明                          |
| ------ | --------------------------------- |
| \n     | 换行符，n   是   newline   的意思 |
| \ \    | 斜杠   \                          |
| \'     | '   单引号                        |
| \"     | ”双引号                           |
| \t     | tab  缩进                         |
| \b     | 空格 ，b   是   blank  的意思     |

- 字符串长度

```javascript
var strMsg = "我是一个字符串";
alert(strMsg.length);
```

- 字符串拼接

```javascript
// 用+号

//1.1 字符串 "相加"
alert('hello' + ' ' + 'world'); // hello world
//1.2 数值字符串 "相加"
alert('100' + '100'); // 100100
//1.3 数值字符串 + 数值
alert('11' + 12);     // 1112 
```

### 布尔型Boolean

```javascript
// 布尔型和数字型相加
console.log(true + 1);  // 2
console.log(false + 1); // 1
```

### Undefined和Null

```javascript
// 变量声明但未赋值->默认值undefined
var variable;
console.log(variable);           // undefined
console.log('你好' + variable);  // 你好undefined
console.log(11 + variable);     // NaN
console.log(true + variable);   //  NaN

// 声明变量并赋值为null
var vari = null;
console.log('你好' + vari);  // 你好null
console.log(11 + vari);     // 11
console.log(true + vari);   //  1
```

### 获取变量数据类型

- 获取检测变量的数据类型 typeof

```javascript
var num = 18;
console.log(typeof num)// 结果为number
```

| 类型      | 例               | 结果        |
| --------- | ---------------- | ----------- |
| String    | typeof "好好"    | "string"    |
| Number    | typeof 18        | "number"    |
| Boolean   | typeof true      | "boolean"   |
| Undefined | typeof undefined | "undefined" |
| Null      | typeof null      | "object"    |

- 字面量

  字面量是在源代码中一个固定值的表示法，表示如何表达这个值

- 数字字面量：8,9,10

- 字符串字面量：'大前端'

- 布尔字面量：true，false

### 数据类型转换

- 转换为字符串

| 方式               | 说明                 | 案例                               |
| ------------------ | -------------------- | ---------------------------------- |
| toString()         | 转成字符串           | var num = 1; alert(num.toString()) |
| String()强制转换   | 转成字符串           | alert(String(num))                 |
| **加号拼接字符串** | 利用算数运算隐式转换 | '12' + 0                           |

- 转换为数字型

| 方式               | 说明                         | 案例                |
| ------------------ | ---------------------------- | ------------------- |
| parseInt(string)   | 将string类型转成整数数值型   | parseInt('78')      |
| parseFloat(string) | 将string类型转成浮点数数值型 | parseFloat('78.21') |
| Number()强制转换   | 将string类型转换为数值型     | Number('12')        |
| js隐式转换(- * /)  | 利用算数运算隐式转换为数值型 | '12' - 0            |

- 转换为布尔型

| 方式      | 说明               | 案例             |
| --------- | ------------------ | ---------------- |
| Boolean() | 其它类型转成布尔型 | Boolean('true'); |

- 代表空、否定的值会被转换为 false  ，如 ''、0、NaN、null、undefined  
- 其余值都会被转换为 true

## 关键字和保留字

### 标识符

```
标识(zhi)符：就是指开发人员为变量、属性、函数、参数取的名字。

标识符不能是关键字或保留字。
```

### 关键字

```
关键字：是指 JS本身已经使用了的字，不能再用它们充当变量名、方法名。

包括：break、case、catch、continue、default、delete、do、else、finally、for、function、if、in、instanceof、new、return、switch、this、throw、try、typeof、var、void、while、with 等。
```

### 保留字

```
保留字：实际上就是预留的“关键字”，意思是现在虽然还不是关键字，但是未来可能会成为关键字，同样不能使用它们当变量名或方法名。

包括：boolean、byte、char、class、const、debugger、double、enum、export、extends、fimal、float、goto、implements、import、int、interface、long、mative、package、private、protected、public、short、static、super、synchronized、throws、transient、volatile 等。

注意：如果将保留字用作变量名或函数名，那么除非将来的浏览器实现了该保留字，否则很可能收不到任何错误消息。当浏览器将其实现后，该单词将被看做关键字，如此将出现关键字错误。
```

## 运算符（操作符）

### 算数运算符

| 运算符 | 描述           | 实例                    |
| ------ | -------------- | ----------------------- |
| +      | 加             | 10 + 20 = 30            |
| -      | 减             | 10 - 20 = -10           |
| *      | 乘             | 10 * 20 =200            |
| /      | 除             | 10 / 20 = 0.5           |
| %      | 取余数（取模） | 返回除数的余数9 % 2 = 1 |

- 浮点数精度问题

  浮点数值最高精度17位小数，但进行算数计算时其精度远不如整数

  ```javascript
  var result = 0.1 + 0.2;    // 结果不是 0.3，而是：0.30000000000000004
  console.log(0.07 * 100);   // 结果不是 7，  而是：7.000000000000001
  ```

  所以不要直接判断两个浮点数是否相等

- 表达式和返回值

  表达式：是由数字、运算符、变量等以能求得数值的有意义排列方法所得的组合

  简单理解：是由数字、运算符、变量等组成的式子

  表达式最终都会有一个结果，返回给开发者，称为返回值

### 递增和递减运算符

- 递增和递减运算符概述

  如果需要反复给数字变量添加或减去1，可以使用递增（++）和递减（ -- ）运算符来完成。

    	在 JavaScript 中，递增（++）和递减（ -- ）既可以放在变量前面，也可以放在变量后面。放在变量前面时，我们可以称为前置递增（递减）运算符，放在变量后面时，我们可以称为后置递增（递减）运算符。

    	注意：递增和递减运算符必须和变量配合使用。

- 递增运算符

  - 前置递增运算符

    ++num 前置递增，就是自加1，类似于 num =  num + 1，但是 ++num 写起来更简单。

    使用口诀：先自加，后返回值

  ```js
  var  num = 10;
  alert(++num + 10);   // 21
  ```

  - 后置递增运算符

    num++ 后置递增，就是自加1，类似于 num =  num + 1 ，但是 num++ 写起来更简单。

    使用口诀：先返回原值，后自加 

  ```js
  var  num = 10;
  alert(10 + num++);  // 20
  ```

### 比较运算符

返回布尔值

| 运算符名称 | 说明                         | 案例        | 结果  |
| ---------- | ---------------------------- | ----------- | ----- |
| <          | 小于号                       | 1 < 2       | true  |
| >          | 大于号                       | 1 > 2       | false |
| >=         | 大于等于                     | 2 >= 2      | true  |
| <=         | 小于等于                     | 3 <= 2      | false |
| ==         | 判等号                       | 37 == 37    | true  |
| !=         | 不等号                       | 37 != 37    | false |
| ===   !==  | 全等(要求值和数据类型都一致) | 37 === '37' | false |

### 逻辑运算符

逻辑运算符是用来进行布尔值运算的运算符，其返回值也是布尔值

| 逻辑运算符 | 说明          | 案例            |
| ---------- | ------------- | --------------- |
| &&         | 逻辑与/与/and | true && false   |
| \|\|       | 逻辑或/或/or  | true \|\| false |
| !          | 逻辑非/非/not | !true           |

- 短路运算（逻辑中断）

  短路运算的原理：当有多个表达式（值）时,左边的表达式值可以确定结果时,就不再继续运算右边的表达式的值;

  - 逻辑与

    语法： 表达式1 && 表达式2

        - 如果第一个表达式的值为真，则返回表达式2
        
        - 如果第一个表达式的值为假，则返回表达式1

    ```js
    console.log( 123 && 456 );        // 456
    console.log( 0 && 456 );          // 0 
    console.log( 123 && 456 && 789 );  // 789
    ```

  - 逻辑或

    语法： 表达式1 || 表达式2

        - 如果第一个表达式的值为真，则返回表达式1
        
        - 如果第一个表达式的值为假，则返回表达式2

     ```js
     console.log( 123 || 456 );         //  123
     console.log( 0 ||  456 );          //  456
     console.log( 123 || 456 || 789 );  //  123
     ```

###  赋值运算符

| 赋值运算符 | 说明                 | 案例                          |
| ---------- | -------------------- | ----------------------------- |
| =          | 直接赋值             | var usrName = '好好'          |
| +=、-=     | 加、减一个数后再赋值 | var age = 10; age += 5; // 15 |
| *=、/=、%= | 乘、除、取模后再赋值 | var age = 2; age *= 5; // 10  |

### 运算符优先级

| 优先级 | 运算符     | 顺序              |
| ------ | ---------- | ----------------- |
| 1      | 小括号     | ( )               |
| 2      | 一元运算符 | ++  --  !         |
| 3      | 算符运算符 | *  /  %  +  -     |
| 4      | 关系运算符 | >  >=  <  <=      |
| 5      | 相等运算符 | ==   !=  ===  !== |
| 6      | 逻辑运算符 | &&  \|\|          |
| 7      | 赋值运算符 | =                 |
| 8      | 逗号运算符 | ,                 |

- 一元运算符里面的逻辑非优先级很高
- 逻辑与比逻辑或优先级高

## 流程控制

### 顺序流程控制

按照代码的先后顺序，依次执行

### 分支流程控制

- if语句

  ```javascript
  // 条件成立执行代码，否则什么也不做
  if (条件表达式) {
      // 条件成立执行的代码语句
  }
  ```

- if else语句（双分支语句）

  ```javascript
  // 条件成立  执行 if 里面代码，否则执行else 里面的代码
  if (条件表达式) {
      // [如果] 条件成立执行的代码
  } else {
      // [否则] 执行的代码
  }
  ```

- if else if 语句(多分支语句)

  ```javascript
  // 适合于检查多重条件。
  if (条件表达式1) {
      语句1；
  } else if (条件表达式2)  {
      语句2；
  } else if (条件表达式3)  {
     语句3；
   ....
  } else {
      // 上述条件都不成立执行此处代码
  }
  ```

### 三元表达式

``` javascript
表达式1 ? 表达式2 : 表达式3;
```

### switch分支流程控制

```javascript
switch( 表达式 ){ 
    case value1:
        // 表达式 等于 value1 时要执行的代码
        break;
    case value2:
        // 表达式 等于 value2 时要执行的代码
        break;
    default:
        // 表达式 不等于任何一个 value 时要执行的代码
}
```

- 关键字 switch 后面括号内可以是表达式或值， 通常是一个变量

- 关键字 case , 后跟一个选项的表达式或值，后面跟一个冒号

- switch 表达式的值会与结构中的 case 的值做比较 

- 如果存在匹配全等(===) ，则与该 case 关联的代码块会被执行，并在遇到 break 时停止，整个 switch 语句代码执行结束

- 如果所有的 case 的值都和表达式的值不匹配，则执行 default 里的代码

  **注意： 执行case 里面的语句时，如果没有break，则继续执行下一个case里面的语句。**

- switch 语句和 if else if 语句的区别

  - 一般情况下，它们两个语句可以相互替换
  - switch...case 语句通常处理 case为比较确定值的情况， 而 if…else…语句更加灵活，常用于范围判断(大于、等于某个范围)
  - switch 语句进行条件判断后直接执行到程序的条件语句，效率更高。而if…else 语句有几种条件，就得判断多少次。
  - 当分支比较少时，if… else语句的执行效率比 switch语句高。
  - 当分支比较多时，switch语句的执行效率比较高，而且结构更清晰。 

## 循环

### for循环

```javascript
for(初始化变量; 条件表达式; 操作表达式 ){
    //循环体
}
```

- | 名称       | 作用                                                         |
  | ---------- | ------------------------------------------------------------ |
  | 初始化变量 | 通常被用于初始化一个计数器，该表达式可以使用 var 关键字声明新的变量，这个变量帮我们来记录次数。 |
  | 条件表达式 | 用于确定每一次循环是否能被执行。如果结果是 true 就继续循环，否则退出循环。 |
  | 操作表达式 | 用于确定每一次循环是否能被执行。如果结果是 true 就继续循环，否则退出循环。 |

  执行过程：

  1. 初始化变量，初始化操作在整个 for 循环只会执行一次。

- 执行条件表达式，如果为true，则执行循环体语句，否则退出循环，循环结束。

1. 执行操作表达式，此时第一轮结束。
2. 第二轮开始，直接去执行条件表达式（不再初始化变量），如果为 true ，则去执行循环体语句，否则退出循环。
3. 继续执行操作表达式，第二轮结束。
4. 后续跟第二轮一致，直至条件表达式为假，结束整个 for 循环。

断点调试：

```
	断点调试是指自己在程序的某一行设置一个断点，调试时，程序运行到这一行就会停住，然后你可以一步一步往下调试，调试过程中可以看各个变量当前的值，出错的话，调试到出错的代码行即显示错误，停下。断点调试可以帮助观察程序的运行过程
```

```html
断点调试的流程：
1、浏览器中按 F12--> sources -->找到需要调试的文件-->在程序的某一行设置断点
2、Watch: 监视，通过watch可以监视变量的值的变化，非常的常用。
3、摁下F11，程序单步执行，让程序一行一行的执行，这个时候，观察watch中变量的值的变化。
```

- for循环重复相同的代码

  ```javascript
  // 用户输入次数
  var num = prompt('请输入次数:')；
  for ( var i = 1 ; i <= num; i++) {
      console.log('媳妇我错了~');
  } 
  ```

### 双重for循环

```javascript
for (外循环的初始; 外循环的条件; 外循环的操作表达式) {
    for (内循环的初始; 内循环的条件; 内循环的操作表达式) {  
       需执行的代码;
   }
}
```

- 内层循环可以看做外层循环的循环体语句

- 内层循环执行的顺序也要遵循 for 循环的执行顺序 

- 外层循环执行一次，内层循环要执行全部次数

- 打印五行五列星星

  ```javascript
  var star = '';
  for (var j = 1; j <= 5; j++) {
      for (var i = 1; i <= 5; i++) {
        star += '☆'
      }
      // 每次满 5个星星 就 加一次换行
      star += '\n'
  }
  console.log(star);
  ```

  核心逻辑：

  1.内层循环负责一行打印五个星星

  2.外层循环负责打印五行

### while循环

```javascript
while (条件表达式) {
    // 循环体代码 
}
```

执行思路：

- 1 先执行条件表达式，如果结果为 true，则执行循环体代码；如果为 false，则退出循环，执行后面代码
- 2 执行循环体代码
- 3 循环体代码执行完毕后，程序会继续判断执行条件表达式，如条件仍为true，则会继续执行循环体，直到循环条件为 false 时，整个循环过程才会结束

注意：

- 使用 while 循环时一定要注意，它必须要有退出条件，否则会成为死循环

### do...while循环

```javascript
do {
    // 循环体代码 - 条件表达式为 true 时重复执行循环体代码
} while(条件表达式);
```

- 1 先执行一次循环体代码 

- 2 再执行条件表达式，如果结果为 true，则继续执行循环体代码，如果为 false，则退出循环，继续执行后面代码	

  注意：先再执行循环体，再判断，do…while循环语句至少会执行一次循环体代码

### continue、break

- continue 关键字用于立即跳出本次循环，继续下一次循环（本次循环体中 continue 之后的代码就会少执行一次）
- break 关键字用于立即跳出整个循环（循环结束）

## 数组

### 创建数组

- 利用  new 创建数组  

  ```js
  var 数组名 = new Array();
  var arr = new Array();   // 创建一个新的空数组
  ```

  注意 Array () ，A 要大写    

- 利用数组字面量创建数组

  ```js
  //1. 使用数组字面量方式创建空的数组
  var  数组名 = [];
  //2. 使用数组字面量方式创建带初始值的数组
  var  数组名 = ['小白','小黑','大黄','瑞奇'];
  ```

  - 数组的字面量是方括号 [ ] 
  - 声明数组并赋值称为数组的初始化
  - 这种字面量方式也是我们以后最多使用的方式

- 数组元素的类型

  数组中可以存放任意类型的数据，例如字符串，数字，布尔值等。

  ```js
  var arrStus = ['小白',12,true,28.9];
  ```

### 获取数组中的元素

​	索引 (下标) ：用来访问数组元素的序号（数组下标从 0 开始）。

注意：如果访问时数组没有和索引值对应的元素，则得到的值是undefined

### 遍历数组

- 数组遍历

  ​		把数组中的每个元素从头到尾都访问一次（类似学生的点名），可以通过 for 循环索引遍历数组中的每一项


```js
var arr = ['red','green', 'blue'];
for(var i = 0; i < arr.length; i++){
    console.log(arrStus[i]);
}
```

- 数组的长度

  数组的长度：默认情况下表示数组中元素的个数

  使用“数组名.length”可以访问数组元素的数量（数组长度）。

  ```js
  var arrStus = [1,2,3];
  alert(arrStus.length);  // 3
  ```

    **注意**：

  - 此处数组的长度是数组元素的个数 ，不要和数组的索引号混淆。

- 当我们数组里面的元素个数发生了变化，这个 length 属性跟着一起变化

  - 数组的length属性可以被修改：

- 如果设置的length属性值大于数组的元素个数，则会在数组末尾出现空白元素；

  - 如果设置的length属性值小于数组的元素个数，则会把超过该值的数组元素删除

### 数组中新增元素

数组中可以通过以下方式在数组的末尾插入新元素：

```js
  数组[ 数组.length ] = 新数据;
```

## 函数

函数：就是**封装了一段可被重复调用执行的代码块**。通过此代码块可以**实现大量代码的重复使用**。  

### 声明函数

```javascript
// 声明函数
function 函数名() {
    //函数体代码
}
```

- function 是声明函数的关键字,必须小写
- 由于函数一般是为了实现某个功能才定义的， 所以通常我们将函数名命名为动词，比如 getSum

### 调用函数

```javascript
// 调用函数
函数名();  // 通过调用函数名来执行函数体代码
```

- 调用的时候千万不要忘记添加小括号

- 口诀：函数不调用，自己不执行

  注意：声明函数本身并不会执行代码，只有调用函数时才会执行函数体代码。

### 函数的封装

函数的封装是把一个或者多个功能通过函数的方式封装起来，对外只提供一个简单的函数接口

```javascript
/* 
   计算1-100之间值的函数
*/
// 声明函数
function getSum(){
  var sumNum = 0;// 准备一个变量，保存数字和
  for (var i = 1; i <= 100; i++) {
    sumNum += i;// 把每个数值 都累加 到变量中
  }
  alert(sumNum);
}
// 调用函数
getSum();
```



### 函数的参数

```javascript
// 带参数的函数声明
function 函数名(形参1, 形参2 , 形参3...) { // 可以定义任意多的参数，用逗号分隔
  // 函数体
}
// 带参数的函数调用
函数名(实参1, 实参2, 实参3...); 
```

1. 调用的时候实参值是传递给形参的
2. 形参简单理解为：不用声明的变量
3. 实参和形参的多个参数之间用逗号（,）分隔

#### 函数的形参和实参数量不匹配时

| 参数个数         | 说明                               |
| ---------------- | ---------------------------------- |
| 实参个数等于形参 | 输出正确结果                       |
| 实参个数多于形参 | 只取到形参的个数                   |
| 实参个数小于形参 | 多的形参定义为undefined，结果为NaN |

注意：在JavaScript中，形参的默认值是undefined。

### 函数的返回值

#### return 语句

	返回值：函数调用整体代表的数据；函数执行完成后可以通过return语句将指定数据返回 。

```js
// 声明函数
function 函数名（）{
    ...
    return  需要返回的值；
}
// 调用函数
函数名();    // 此时调用函数就可以得到函数体内return 后面的值
```

-  在使用 return 语句时，函数会停止执行，并返回指定的值
-  如果函数没有 return ，返回的值是 undefined

#### break ,continue ,return 的区别

- break ：结束当前的循环体（如 for、while）
- continue ：跳出本次循环，继续执行下次循环（如 for、while）
- return ：不仅可以退出循环，还能够返回 return 语句中的值，同时还可以结束当前的函数体内的代码

### arguments的使用

​			当不确定有多少个参数传递的时候，可以用 arguments 来获取。JavaScript 中，arguments实际上它是当前函数的一个内置对象。所有函数都内置了一个 arguments 对象，arguments 对象中存储了传递的所有实参。arguments展示形式是一个伪数组，因此可以进行遍历。伪数组具有以下特点：

- 具有 length 属性

- 按索引方式储存数据

- 不具有数组的 push , pop 等方法

  注意：在函数内部使用该对象，用此对象获取函数调用时传的实参。

### 函数的两种声明方式

- 自定义函数方式(命名函数)

  利用函数关键字 function 自定义函数方式

  ```js
  // 声明定义方式
  function fn() {...}
  // 调用  
  fn();  
  ```

  - 因为有名字，所以也被称为命名函数
  - 调用函数的代码既可以放到声明函数的前面，也可以放在声明函数的后面

- 函数表达式方式(匿名函数）

  利用函数表达式方式的写法如下： 

  ```js
  // 这是函数表达式写法，匿名函数后面跟分号结束
  var fn = function(){...}；
  // 调用的方式，函数调用必须写到函数体下面
  fn();
  ```

  - 因为函数没有名字，所以也被称为匿名函数
  - 这个fn 里面存储的是一个函数  
  - 函数表达式方式原理跟声明变量方式是一致的
  - 函数调用的代码必须写到函数体后面

## 作用域

### 作用域概述

	通常来说，一段程序代码中所用到的名字并不总是有效和可用的，而限定这个名字的可用性的代码范围就是这个名字的作用域。作用域的使用提高了程序逻辑的局部性，增强了程序的可靠性，减少了名字冲突。
	
	JavaScript（es6前）中的作用域有两种：

- 全局作用域
- 局部作用域（函数作用域）	

### 全局作用域

	作用于所有代码执行的环境(整个 script 标签内部)或者一个独立的 js 文件。

### 局部作用域

	作用于函数内的代码环境，就是局部作用域。 因为跟函数有关系，所以也称为函数作用域。

### JS没有块级作用域

- 块作用域由 { } 包括。

- 在其他编程语言中（如 java、c#等），在 if 语句、循环语句中创建的变量，仅仅只能在本 if 语句、本循环语句中使用，如下面的Java代码：	

  java有块级作用域：

  ```java
  if(true){
    int num = 123;
    system.out.print(num);  // 123
  }
  system.out.print(num);    // 报错
  ```

  以上java代码会报错，是因为代码中 { } 即一块作用域，其中声明的变量 num，在 “{ }” 之外不能使用；

  而与之类似的JavaScript代码，则不会报错：



###   Js中没有块级作用域（在ES6之前）

  ```js
  if(true){
    var num = 123;
    console.log(123); //123
  }
  console.log(123);   //123
  ```

## 变量的作用域

	在JavaScript中，根据作用域的不同，变量可以分为两种：

- 全局变量
- 局部变量

### 全局变量

	在全局作用域下声明的变量叫做全局变量（在函数外部定义的变量）。

- 全局变量在代码的任何位置都可以使用
- 在全局作用域下 var 声明的变量 是全局变量
- 特殊情况下，在函数内不使用 var 声明的变量也是全局变量（不建议使用）

### 局部变量

	在局部作用域下声明的变量叫做局部变量（在函数内部定义的变量）

- 局部变量只能在该函数内部使用
- 在函数内部 var 声明的变量是局部变量
- 函数的形参实际上就是局部变量

### 全局变量和局部变量的区别

- 全局变量：在任何一个地方都可以使用，只有在浏览器关闭时才会被销毁，因此比较占内存
- 局部变量：只在函数内部使用，当其所在的代码块被执行时，会被初始化；当代码块运行结束后，就会被销毁，因此更节省内存空间

## 作用域链

```
只要是代码都一个作用域中，写在函数内部的局部作用域，未写在任何函数内部即在全局作用域中；如果函数中还有函数，那么在这个作用域中就又可以诞生一个作用域；根据在**[内部函数可以访问外部函数变量]**的这种机制，用链式查找决定哪些数据能被内部函数访问，就称作作用域链
```

```js
//案例分析1
function f1() {
    var num = 123;
    function f2() {
        console.log( num );
    }
    f2();
}
var num = 456;
f1();// 123
```

```
作用域链：采取就近原则的方式来查找变量最终的值。
```

```js
var a = 1;
function fn1() {
    var a = 2;
    var b = '22';
    fn2();
    function fn2() {
        var a = 3;
        fn3();
        function fn3() {
            var a = 4;
            console.log(a); //a的值 ?   4
            console.log(b); //b的值 ?   '22'
        }
    }
}
fn1();
```

![](images\作用域链.png)

## 预解析

### 预解析的相关概念

	JavaScript 代码是由浏览器中的 JavaScript 解析器来执行的。JavaScript 解析器在运行 JavaScript 代码的时候分为两步：预解析和代码执行。

- 预解析：在当前作用域下, JS 代码执行之前，浏览器会默认把带有 var 和 function 声明的变量在内存中进行提前声明或者定义。

- 代码执行： 从上到下执行JS语句。

  **预解析会把变量和函数的声明在代码执行之前执行完成。**

### 变量预解析

	预解析也叫做变量、函数提升。
	变量提升（变量预解析）： 变量的声明会被提升到当前作用域的最上面，变量的赋值不会提升。

```js
console.log(num);  // 结果是多少？
var num = 10;      // ？
```

	结果：undefined
	
	注意：**变量提升只提升声明，不提升赋值**

### 函数预解析

	函数提升： 函数的声明会被提升到当前作用域的最上面，但是不会调用函数。

```js
fn();
function fn() {
    console.log('打印');
}
```

	结果：控制台打印字符串 --- ”打印“ 
	
	注意：函数声明代表函数整体，所以函数提升后，函数名代表整个函数，但是函数并没有被调用！	

### 函数表达式声明函数问题

	函数表达式创建函数，会执行变量提升，此时接收函数的变量名无法正确的调用：

```js
fn();
var  fn = function() {
    console.log('想不到吧');
}
```

	结果：报错提示 ”fn is not a function"
	
	解释：该段代码执行之前，会做变量声明提升，fn在提升之后的值是undefined；而fn调用是在fn被赋值为函数体之前，此时fn的值是undefined，所以无法正确调用

## 对象

### 对象的相关概念

- 什么是对象？

  在 JavaScript 中，对象是一组无序的相关属性和方法的集合，所有的具体的事物都是对象，例如字符串、数值、数组、函数等。
   	对象是由属性和方法组成的。

  - 属性：事物的特征，在对象中用属性来表示（常用名词）

  - 方法：事物的行为，在对象中用方法来表示（常用动词）

```js
var obj = {
    "name":"张三疯",
    "sex":"男",
    "age":128,
    "height":154
}
```

### 创建对象的三种方式

- 利用字面量创建对象 

  #####     **使用对象字面量创建对象**：

  		就是花括号 { } 里面包含了表达这个具体事物（对象）的属性和方法；{ } 里面采取键值对的形式表示 

  - 键：相当于属性名

  - 值：相当于属性值，可以是任意类型的值（数字类型、字符串类型、布尔类型，函数类型等）

    代码如下：

    ```js
    var star = {
        name : 'pink',
        age : 18,
        sex : '男',
        sayHi : function(){
            alert('大家好啊~');
        }
    };
    ```

    上述代码中 star即是创建的对象。

- 对象的使用

  - 对象的属性

    - 对象中存储**具体数据**的 "键值对"中的 "键"称为对象的属性，即对象中存储具体数据的项

  - 对象的方法

    - 对象中存储**函数**的 "键值对"中的 "键"称为对象的方法，即对象中存储函数的项

  - 访问对象的属性

    - 对象里面的属性调用 : 对象.属性名 ，这个小点 . 就理解为“ 的 ”  

    - 对象里面属性的另一种调用方式 : 对象[‘属性名’]，注意方括号里面的属性必须加引号      

      示例代码如下：

      ```js
      console.log(star.name)     // 调用名字属性
      console.log(star['name'])  // 调用名字属性
      ```

  - 调用对象的方法

    - 对象里面的方法调用：对象.方法名() ，注意这个方法名字后面一定加括号 

      示例代码如下：

      ```js
      star.sayHi();              // 调用 sayHi 方法,注意，一定不要忘记带后面的括号
      ```

  - 变量、属性、函数、方法总结

    属性是对象的一部分，而变量不是对象的一部分，变量是单独存储数据的容器

    - 变量：单独声明赋值，单独存在
    - 属性：对象里面的变量称为属性，不需要声明，用来描述该对象的特征



    	方法是对象的一部分，函数不是对象的一部分，函数是单独封装操作的容器
    
    - 函数：单独存在的，通过“函数名()”的方式就可以调用
    - 方法：对象里面的函数称为方法，方法不需要声明，使用“对象.方法名()”的方式就可以调用，方法用来描述该对象的行为和功能。 

- 利用 new Object 创建对象 

  - 创建空对象

    ```js
    var andy = new Obect();
    ```

    通过内置构造函数Object创建对象，此时andy变量已经保存了创建出来的空对象

  - 给空对象添加属性和方法

    - 通过对象操作属性和方法的方式，来为对象增加属性和方法

      示例代码如下：

    ```js
    andy.name = 'pink';
    andy.age = 18;
    andy.sex = '男';
    andy.sayHi = function(){
        alert('大家好啊~');
    }
    ```

    注意：

    - Object() ：第一个字母大写   
    - new Object() ：需要 new 关键字
    - 使用的格式：对象.属性 =  值;     

- 利用构造函数创建对象

  - 构造函数

    - 构造函数：是一种特殊的函数，主要用来初始化对象，即为对象成员变量赋初始值，它总与 new 运算符一起使用。我们可以把对象中一些公共的属性和方法抽取出来，然后封装到这个函数里面。

    - 构造函数的封装格式：

      ```js
      function 构造函数名(形参1,形参2,形参3) {
           this.属性名1 = 参数1;
           this.属性名2 = 参数2;
           this.属性名3 = 参数3;
           this.方法名 = 函数体;
      }
      ```

    - 构造函数的调用格式

      ```
      var obj = new 构造函数名(实参1，实参2，实参3)
      ```

      以上代码中，obj即接收到构造函数创建出来的对象。

    - 注意事项

      1.   构造函数约定**首字母大写**。
      2.   函数内的属性和方法前面需要添加 **this** ，表示当前对象的属性和方法。
      3.   构造函数中**不需要 return 返回结果**。
      4.   当我们创建对象的时候，**必须用 new 来调用构造函数**。

    - 其他

      构造函数，如 Stars()，抽象了对象的公共部分，封装到了函数里面，它泛指某一大类（class）  
      创建对象，如 new Stars()，特指某一个，通过 new 关键字创建对象的过程我们也称为对象实例化

- new关键字的作用

  1. 在构造函数代码开始执行之前，创建一个空对象；
  2. 修改this的指向，把this指向创建出来的空对象；
  3. 执行函数的代码
  4. 在函数完成之后，返回this---即创建出来的对象

### 遍历对象

```
for...in 语句用于对数组或者对象的属性进行循环操作。

其语法如下：
```

```js
for (变量 in 对象名字) {
    // 在此执行代码
}
```

```
语法中的变量是自定义的，它需要符合命名规范，通常我们会将这个变量写为 k 或者 key。
```

```js
for (var k in obj) {
    console.log(k);      // 这里的 k 是属性名
    console.log(obj[k]); // 这里的 obj[k] 是属性值
}
```

### 内置对象

 		JavaScript 中的对象分为3种：**自定义对象 、内置对象、 浏览器对象**
		前面两种对象是JS 基础 内容，属于 ECMAScript；  第三个浏览器对象属于 JS 独有的， JS API 讲解内置对象就是指 JS 语言自带的一些对象，这些对象供开发者使用，并提供了一些常用的或是**最基本而必要的功能**（属性和方法），内置对象最大的优点就是帮助我们快速开发

​	 	JavaScript 提供了多个内置对象：Math、 Date 、Array、String等	

#### 查文档

​		查找文档：学习一个内置对象的使用，只要学会其常用成员的使用即可，我们可以通过查文档学习，可以通过MDN/W3C来查询。
​		Mozilla 开发者网络（MDN）提供了有关开放网络技术（Open Web）的信息，包括 HTML、CSS 和万维网及 HTML5 应用的 API。
​		MDN:https://developer.mozilla.org/zh-CN/

#### Math对象

​		Math 对象不是构造函数，它具有数学常数和函数的属性和方法。跟数学相关的运算（求绝对值，取整、最大值等）可以使用 Math 中的成员。

| 属性、方法名          | 功能                                         |
| --------------------- | -------------------------------------------- |
| Math.PI               | 圆周率                                       |
| Math.floor()          | 向下取整                                     |
| Math.ceil()           | 向上取整                                     |
| Math.round()          | 四舍五入版 就近取整   注意 -3.5   结果是  -3 |
| Math.abs()            | 绝对值                                       |
| Math.max()/Math.min() | 求最大和最小值                               |
| Math.random()         | 获取范围在[0,1)内的随机值                    |

​	注意：上面的方法使用时必须带括号

​	**获取指定范围内的随机整数**：

```js
function getRandom(min, max) {
  return Math.floor(Math.random() * (max - min + 1)) + min; 
}
```

#### 日期对象

​	 	Date 对象和 Math 对象不一样，Date是一个构造函数，所以使用时需要实例化后才能使用其中具体方法和属性。Date 实例用来处理日期和时间

- 使用Date实例化日期对象

  - 获取当前时间必须实例化：

  ```js
  var now = new Date();
  ```

  - 获取指定时间的日期对象

  ```js
  var future = new Date('2019/5/1');
  ```

  注意：如果创建实例时并未传入参数，则得到的日期对象是当前时间对应的日期对象

- 使用Date实例的方法和属性	

  | 方法名        | 说明            | 代码               |
  | ------------- | --------------- | ------------------ |
  | getFullYear() | 获取当年        | dObj.getFullYear() |
  | getMonth()    | 获取当月(0-11)  | dObj.getMonth()    |
  | getDate()     | 获取当天日期    | dObj.getDate()     |
  | getDay()      | 获取星期几(0-6) | dObj.getDat()      |
  | getHours()    | 获取当前小时    | dObj.getHours()    |
  | getMinutes()  | 获取当前分钟    | dObj.getMinutes()  |
  | getSeconds()  | 获取当前秒钟    | dObj.getSeconds()  |

- 通过Date实例获取总毫米数

  - 总毫秒数的含义

    ​	基于1970年1月1日（世界标准时间）起的毫秒数

  - 获取总毫秒数

    ```js
    // 实例化Date对象
    var now = new Date();
    // 1. 用于获取对象的原始值
    console.log(date.valueOf())	
    console.log(date.getTime())	
    // 2. 简单写可以这么做
    var now = + new Date();			
    // 3. HTML5中提供的方法，有兼容性问题
    var now = Date.now();
    ```

#### 数组对象

##### 创建数组的两种方式

- 字面量方式

  - 示例代码如下：

    ```js
    var arr = [1,"test",true];
    ```

- new Array()

  - 示例代码如下：

    ```
    var arr = new Array();
    ```

    ​	注意：上面代码中arr创建出的是一个空数组，如果需要使用构造函数Array创建非空数组，可以在创建数组时传入参数

    ​	参数传递规则如下：

    - 如果只传入一个参数，则参数规定了数组的长度

    - 如果传入了多个参数，则参数称为数组的元素

##### 检测是否为数组

- instanceof 运算符

  - instanceof 可以判断一个对象是否是某个构造函数的实例

    ```js
    var arr = [1, 23];
    var obj = {};
    console.log(arr instanceof Array); // true
    console.log(obj instanceof Array); // false
    ```

- Array.isArray()

  - Array.isArray()用于判断一个对象是否为数组，isArray() 是 HTML5 中提供的方法

    ```js
    var arr = [1, 23];
    var obj = {};
    console.log(Array.isArray(arr));   // true
    console.log(Array.isArray(obj));   // false
    ```

##### 添加删除数组元素的方法

| 方法名    | 说明                                              | 返回值             |
| --------- | ------------------------------------------------- | ------------------ |
| push()    | 末尾添加一个或多个元素，修改原数组                | 返回新的长度       |
| pop()     | 删除数组最后一个元素，长度减1，无参数，修改原数组 | 返回删除的元素的值 |
| unshift() | 向数组开头添加一个或多个元素，修改原数组          | 返回新的长度       |
| shift()   | 删除数组第一个元素，长度减1，修改原数组           | 返回第一个元素的值 |

##### 数组排序

| 方法名    | 说明               | 是否修改原数组         |
| --------- | ------------------ | ---------------------- |
| reverse() | 将数组倒序，无参数 | 改变原数组，返回新数组 |
| sort()    | 将数组排序         | 改变原数组，返回新数组 |

注意：sort方法需要传入参数来设置升序、降序排序

- 如果传入“function(a,b){ return a-b;}”，则为升序
- 如果传入“function(a,b){ return b-a;}”，则为降序

##### 数组索引方法

| 方法名        | 说明                               | 返回值                           |
| ------------- | ---------------------------------- | -------------------------------- |
| indexOf()     | 在数组中查找给定元素的第一个索引   | 若存在，返回索引号，不存在返回-1 |
| lastIndexOf() | 在数组中查找给定元素的最后一个索引 | 若存在，返回索引号，不存在返回-1 |



##### 数组转换为字符串

| 方法名         | 说明                                                       | 返回值         |
| -------------- | ---------------------------------------------------------- | -------------- |
| toString()     | 将数组转为字符串，逗号分割                                 | 返回一个字符串 |
| join('分隔符') | 用于把数组中的所有元素转换为一个字符串，分隔符用于替换逗号 | 返回一个字符串 |

##### 其他方法

| 方法      | 说明                             | 返回值                             |
| --------- | -------------------------------- | ---------------------------------- |
| contact() | 连接两个或多个数组，不影响原数组 | 返回一个新数组                     |
| slice()   | 截取数组slice(begin, end)        | 返回截取的新数组                   |
| splice()  | 删除splice(开始索引， 删除个数)  | 返回被删除后的新数组，会影响原数组 |

#### 字符串对象

##### 基本包装类型

​		为了方便操作基本数据类型，JavaScript 还提供了三个特殊的引用类型：String、Number和 Boolean。

​		基本包装类型就是把简单数据类型包装成为复杂数据类型，这样基本数据类型就有了属性和方法。

```js
// 下面代码有什么问题？
var str = 'andy';
console.log(str.length);
```

​		按道理基本数据类型是没有属性和方法的，而对象才有属性和方法，但上面代码却可以执行，这是因为

​		js 会把基本数据类型包装为复杂数据类型，其执行过程如下 ：

```js
// 1. 生成临时变量，把简单类型包装为复杂数据类型
var temp = new String('andy');
// 2. 赋值给我们声明的字符变量
str = temp;
// 3. 销毁临时变量
temp = null;
```

##### 字符串的不可变

​		指的是里面的值不可变，虽然看上去可以改变内容，但其实是地址变了，内存中新开辟了一个内存空间。

​		当重新给字符串变量赋值的时候，变量之前保存的字符串不会被修改，依然在内存中重新给字符串赋值，会重新在内存中开辟空间，这个特点就是字符串的不可变。
​		由于字符串的不可变，在**大量拼接字符串**的时候会有效率问题

##### 根据字符返回位置

| 方法名                              | 说明                                                         |
| ----------------------------------- | ------------------------------------------------------------ |
| indexOf('要查找的字符', 开始的位置) | 返回指定内容在元字符中的位置，找不到返回-1，开始位置是index索引号 |
| lastIndexOf()                       | 从后往前找，只找一个匹配的                                   |

案例：查找字符串"abcoefoxyozzopp"中所有o出现的位置以及次数

1. 先查找第一个o出现的位置
2. 然后 只要indexOf 返回的结果不是 -1 就继续往后查找
3. 因为indexOf 只能查找到第一个，所以后面的查找，利用第二个参数，当前索引加1，从而继续查找 

```js
var str = 'abcoefoxyozzopp';
var index = -1;
var count = -1;
do {
    index = str.indexOf('o', index + 1);
    count++;
    if (index !== -1) {
        console.log('o出现位置' + index);
    }   
} while (index !== -1);
console.log('o出现次数' + count);
```

##### 根据位置返回字符

字符串通过基本包装类型可以调用部分方法来操作字符串，以下是根据位置返回指定位置上的字符：

| 方法名            | 说明                                    | 使用                          |
| ----------------- | --------------------------------------- | ----------------------------- |
| charAt(index)     | 返回指定位置的字符(index字符串的索引号) | str.charAt(0)                 |
| charCodeAt(index) | 获取指定位置处的ASCII码(index索引号)    | str.charCodeAt(0)             |
| str[index]        | 获取指定位置处字符                      | HTML5, IE8+支持和charAt()等效 |

案例：判断一个字符串 'abcoefoxyozzopp' 中出现次数最多的字符，并统计其次数

1. 核心算法：利用 charAt(） 遍历这个字符串

2. 把每个字符都存储给对象， 如果对象没有该属性，就为1，如果存在了就 +1

3. 遍历对象，得到最大值和该字符 	

   ​	注意：在遍历的过程中，把字符串中的每个字符作为对象的属性存储在对象中，对应的属性值是该字符出现的次数

```js
var str = 'abcoefoxyozzopp';
obj = {};
for (var i = 0; i < str.length; i++) {
    var chars = str.charAt(i);
    if (obj[chars]) {
        obj[chars]++;
    } else {
        obj[chars] = 1;
    }
}
console.log(obj);
var max = 0;
var ch = ''
for (key in obj) {
    if (obj[key] > max) {
        max = obj[key];
        ch = key;
    }
}
console.log(ch, max);
```

##### 字符串操作方法

| 方法名                    | 说明                                            |
| ------------------------- | ----------------------------------------------- |
| concat(str1, str2,...)    | concat()方法用于连接两个或多个字符串，+号更常用 |
| **substr(start, length)** | **从strat位置开始，length取的个数**             |
| slice(start, end)         | 从start开始，截取到end，end取不到               |
| substring(start, end)     | 从start开始，截取到end，end取不到，不接受负值   |

##### replace()方法

​		replace() 方法用于在字符串中用一些字符替换另一些字符，其使用格式如下：  

```
字符串.replace(被替换的字符串， 要替换为的字符串)；
```

##### split()方法

​		split()方法用于切分字符串，它可以将字符串切分为数组。在切分完毕之后，返回的是一个新数组。

​		其使用格式如下：

```
字符串.split("分割字符")
```

## 简单数据类型和复杂数据类型

### 简单数据类型

​		**简单类型**（**基本数据类型**、**值类型**）：在存储时变量中存储的是值本身，包括string ，number，boolean，undefined，null

### 复杂数据类型

​		**复杂数据类型（引用类型）**：在存储时变量中存储的仅仅是地址（引用），通过 new 关键字创建的对象（系统对象、自定义对象），如 Object、Array、Date等；

### 简单类型传参

​		函数的形参也可以看做是一个变量，当我们把一个值类型变量作为参数传给函数的形参时，其实是把变量在栈空间里的值复制了一份给形参，那么在方法内部对形参做任何修改，都不会影响到的外部变量。

```js
function fn(a) {
    a++;
    console.log(a); 
}
var x = 10;
fn(x);
console.log(x);

// 11 10
```

### 复杂数据类型传参

​		函数的形参也可以看做是一个变量，当我们把引用类型变量传给形参时，其实是把变量在栈空间里保存的堆地址复制给了形参，形参和实参其实保存的是同一个堆地址，所以操作的是同一个对象。

```JavaScript
function Person(name) {
    this.name = name;
}
function f1(x) { // x = p
    console.log(x.name); // 2. 这个输出什么 ?   
    x.name = "张学友";
    console.log(x.name); // 3. 这个输出什么 ?   
}
var p = new Person("刘德华");
console.log(p.name);    // 1. 这个输出什么 ?  
f1(p);
console.log(p.name);    // 4. 这个输出什么 ?  


//刘德华 刘德华 张学友 张学友
```

# Web APIs

## DOM

### 什么是DOM

​	文档对象模型（Document Object Model，简称DOM），是 [W3C](https://baike.baidu.com/item/W3C) 组织推荐的处理[可扩展标记语言](https://baike.baidu.com/item/%E5%8F%AF%E6%89%A9%E5%B1%95%E7%BD%AE%E6%A0%87%E8%AF%AD%E8%A8%80)（html或者xhtml）的标准[编程接口](https://baike.baidu.com/item/%E7%BC%96%E7%A8%8B%E6%8E%A5%E5%8F%A3)。

​	W3C 已经定义了一系列的 DOM 接口，通过这些 DOM 接口可以改变网页的内容、结构和样式。

### DOM树

![DOM树](C:\Users\Administrator\Desktop\images\DOM树.png)

DOM树 又称为文档树模型，把文档映射成树形结构，通过节点对象对其处理，处理的结果可以加入到当前的页面。

- 文档：一个页面就是一个文档，DOM中使用document表示
- 节点：网页中的所有内容，在文档树中都是节点（标签、属性、文本、注释等），使用node表示
- 标签节点：网页中的所有标签，通常称为元素节点，又简称为“元素”，使用element表示

### 获取元素

为什么要获取页面元素？

例如：我们想要操作页面上的某部分(显示/隐藏，动画)，需要先获取到该部分对应的元素，再对其进行操作。

#### 根据ID获取

```js
语法：document.getElementById(id)
作用：根据ID获取元素对象
参数：id值，区分大小写的字符串
返回值：元素对象 或 null
```

**案例代码**

```js
<body>
    <div id="time">2019-9-9</div>
    <script>
        // 因为我们文档页面从上往下加载，所以先得有标签 所以我们script写到标签的下面
        var timer = document.getElementById('time');
        console.log(timer);
        console.log(typeof timer);
        // console.dir 打印我们返回的元素对象 更好的查看里面的属性和方法
        console.dir(timer);
    </script>
</body>
```

#### 根据标签名获取元素

```js
语法：document.getElementsByTagName('标签名') 或者 element.getElementsByTagName('标签名') 
作用：根据标签名获取元素对象
参数：标签名
返回值：元素对象集合（伪数组，数组元素是元素对象）
```

**案例代码**

```javascript
<body>
    <ul>
        <li>知否知否，应是等你好久11</li>
        <li>知否知否，应是等你好久22</li>
        <li>知否知否，应是等你好久33</li>
        <li>知否知否，应是等你好久44</li>
        <li>知否知否，应是等你好久55</li>
    </ul>
    <ul id="nav">
        <li>生僻字</li>
        <li>生僻字</li>
        <li>生僻字</li>
        <li>生僻字</li>
        <li>生僻字</li>
    </ul>
    <script>
        // 1.返回的是 获取过来元素对象的集合 以伪数组的形式存储的
        var lis = document.getElementsByTagName('li');
        console.log(lis);
        console.log(lis[0]);
        // 2. 我们想要依次打印里面的元素对象我们可以采取遍历的方式
        for (var i = 0; i < lis.length; i++) {
            console.log(lis[i]);
        }
        // 3. element.getElementsByTagName()  可以得到这个元素里面的某些标签
        var nav = document.getElementById('nav'); // 这个获得nav 元素
        var navLis = nav.getElementsByTagName('li');
        console.log(navLis);
    </script>
</body>

```

注意：

1. 因为得到的是一个对象的集合，所以我们想要操作里面的元素就需要遍历
2. 获取到的是动态集合，即：当页面增加了标签，这个集合中也就增加了元素。

#### H5新增获取元素方式

```js
document.getElementsByClassName('类名');// 根据类名返回元素对象集合

document.querySelector('选择器');// 根据指定选择器返回第一个元素对象

document.querySelectorAll('选择器');//根据指定选择器返回

注意：querySelector和querySelectorAll里面的选择器需要加符号，如：document.querySelector('#nav');
```

**案例代码**

```js
<body>
    <div class="box">盒子1</div>
    <div class="box">盒子2</div>
    <div id="nav">
        <ul>
            <li>首页</li>
            <li>产品</li>
        </ul>
    </div>
    <script>
        // 1. getElementsByClassName 根据类名获得某些元素集合
        var boxs = document.getElementsByClassName('box');
        console.log(boxs);
        // 2. querySelector 返回指定选择器的第一个元素对象  切记 里面的选择器需要加符号 .box  #nav
        var firstBox = document.querySelector('.box');
        console.log(firstBox);
        var nav = document.querySelector('#nav');
        console.log(nav);
        var li = document.querySelector('li');
        console.log(li);
        // 3. querySelectorAll()返回指定选择器的所有元素对象集合
        var allBox = document.querySelectorAll('.box');
        console.log(allBox);
        var lis = document.querySelectorAll('li');
        console.log(lis);
    </script>
</body>
```

#### 获取特殊元素(body, html)

```js
// 获取body元素
document.body // 返回body元素对象

// 获取html元素
document.documentElement // 返回html元素对象
```

### 事件基础

#### 事件三要素

- 事件源（谁）：触发事件的元素
- 事件类型（什么事件）： 例如 click 点击事件
- 事件处理程序（做啥）：事件触发后要执行的代码(函数形式)，事件处理函数

**案例代码**

```js
<body>
    <button id="btn">唐伯虎</button>
    <script>
        // 点击一个按钮，弹出对话框
        // 1. 事件是有三部分组成  事件源  事件类型  事件处理程序   我们也称为事件三要素
        //(1) 事件源 事件被触发的对象   谁  按钮
        var btn = document.getElementById('btn');
        //(2) 事件类型  如何触发 什么事件 比如鼠标点击(onclick) 还是鼠标经过 还是键盘按下
        //(3) 事件处理程序  通过一个函数赋值的方式 完成
        btn.onclick = function() {
            alert('点秋香');
        }
    </script>
</body>
```

#### 执行事件的步骤

1. 获取事件源
2. 注册事件（绑定事件）
3. 添加事件处理程序（采取函数赋值形式）

**案例代码**

```js
<body>
    <div>123</div>
    <script>
        // 执行事件步骤
        // 点击div 控制台输出 我被选中了
        // 1. 获取事件源
        var div = document.querySelector('div');
        // 2.绑定事件 注册事件
        // div.onclick 
        // 3.添加事件处理程序 
        div.onclick = function() {
            console.log('我被选中了');
        }
    </script>
</body>
```

#### 常见的鼠标事件

| 鼠标事件    | 触发条件         |
| ----------- | ---------------- |
| onclick     | 鼠标点击左键触发 |
| onmouseover | 鼠标经过触发     |
| onmouseout  | 鼠标离开时触发   |
| onfocus     | 获得鼠标焦点触发 |
| onblur      | 失去鼠标焦点触发 |
| onmousemove | 鼠标移动触发     |
| onmouseup   | 鼠标弹起触发     |
| onmousedown | 鼠标按下触发     |

###  操作元素

​	JavaScript的 DOM 操作可以改变网页内容、结构和样式，我们可以利用 DOM 操作元素来改变元素里面的内容、属性等。（注意：这些操作都是通过元素对象的属性实现的）

#### 改变元素内容（获取或设置）

```js
// 从起始位置到终止位置的内容，但是去除html标签，同时空格和换行也会去掉
element.innerText

// 起始位置到终止位置的全部内容，包括html标签，同时保留空格和换行
element.innerHTML
```

**innerText改变元素内容**

```js
<body>
    <button>显示当前系统时间</button>
    <div>某个时间</div>
    <p>1123</p>
    <script>
        // 当我们点击了按钮，  div里面的文字会发生变化
        // 1. 获取元素 
        var btn = document.querySelector('button');
        var div = document.querySelector('div');
        // 2.注册事件
        btn.onclick = function() {
            // div.innerText = '2019-6-6';
            div.innerHTML = getDate();
        }
        function getDate() {
            var date = new Date();
            // 我们写一个 2019年 5月 1日 星期三
            var year = date.getFullYear();
            var month = date.getMonth() + 1;
            var dates = date.getDate();
            var arr = ['星期日', '星期一', '星期二', '星期三', '星期四', '星期五', '星期六'];
            var day = date.getDay();
            return '今天是：' + year + '年' + month + '月' + dates + '日 ' + arr[day];
        }
    </script>
</body>
```

**innerText和innerHTML的区别**

- 获取内容时的区别：

​	innerText会去除空格和换行，而innerHTML会保留空格和换行	

- 设置内容时的区别：

​	innerText不会识别html，而innerHTML会识别

**案例代码**

```js
<body>
    <div></div>
    <p>
        我是文字
        <span>123</span>
    </p>
    <script>
        // innerText 和 innerHTML的区别 
        // 1. innerText 不识别html标签 非标准  去除空格和换行
        var div = document.querySelector('div');
        // div.innerText = '<strong>今天是：</strong> 2019';
        // 2. innerHTML 识别html标签 W3C标准 保留空格和换行的
        div.innerHTML = '<strong>今天是：</strong> 2019';
        // 这两个属性是可读写的  可以获取元素里面的内容
        var p = document.querySelector('p');
        console.log(p.innerText);
        console.log(p.innerHTML);
    </script>
</body>
```

#### 常见元素的属性操作

1. innerText、innerHTML 改变元素内容
2. src、href
3. id、alt、title

**案例代码**

```js
<body>
    <button id="ldh">刘德华</button>
    <button id="zxy">张学友</button> <br>
    <img src="images/ldh.jpg" alt="" title="刘德华">
    <script>
        // 修改元素属性  src
        // 1. 获取元素
        var ldh = document.getElementById('ldh');
        var zxy = document.getElementById('zxy');
        var img = document.querySelector('img');
        // 2. 注册事件  处理程序
        zxy.onclick = function() {
            img.src = 'images/zxy.jpg';
            img.title = '张学友思密达';
        }
        ldh.onclick = function() {
            img.src = 'images/ldh.jpg';
            img.title = '刘德华';
        }
    </script>
</body>
```

#### 案例：分时问候

![分时问候1](C:\Users\Administrator\Desktop\WebNote\第三部分 JavaScript网络编程\images\分时问候1.png)

![分时问候2](C:\Users\Administrator\Desktop\WebNote\第三部分 JavaScript网络编程\images\分时问候2.png)

```js
<body>
    <div>
        <img src="images/s.gif" style="width: 300px;"/>
        <h2>上午好</h2>
    </div>

    <script>
        // 1.获取元素
        var img = document.querySelector('img');
        var h2 = document.querySelector('h2');
        // 2.得到当前的小时数
        var date = new Date();
        var h = date.getHours();
        // 3.判断小时数改变图片和文字信息
        if (h < 12) {
            img.src = 'images/s.gif';
            h2.innerHTML = '亲，上午好！';
        } else if (h < 18 ) {
            img.src = 'images/x.gif';
            h2.innerHTML = '亲，下午好！';
        } else {
            img.src = 'images/w.gif';
            h2.innerHTML = '亲，晚上好！';
        }
    </script>
</body>
```

#### 表单元素的属性操作

```
利用DOM可以操作如下表单元素属性：
type、value、checked、selected、disabled
```

**案例代码**

```js
<body>
    <button>按钮</button>
    <input type="text" value="输入内容">
    <script>
        // 1. 获取元素
        var btn = document.querySelector('button');
        var input = document.querySelector('input');
        // 2. 注册事件 处理程序
        btn.onclick = function() {
            // 表单里面的值 文字内容是通过 value 来修改的
            input.value = '被点击了';
            // 如果想要某个表单被禁用 不能再点击 disabled  我们想要这个按钮 button禁用
            // btn.disabled = true;
            this.disabled = true;
            // this 指向的是事件函数的调用者 btn
        }
    </script>
</body>
```

#### 案例：仿京东显示密码

![仿京东显示密码1](C:\Users\Administrator\Desktop\WebNote\第三部分 JavaScript网络编程\images\仿京东显示密码1.png)

![仿京东显示密码2](C:\Users\Administrator\Desktop\WebNote\第三部分 JavaScript网络编程\images\仿京东显示密码2.png)

```js
    <style>
        .box {
            position: relative;
            width: 400px;
            border-bottom: 1px solid #ccc;
            margin: 100px auto;
        }

        .box input {
            width: 370px;
            height: 30px;
            border: 0;
            outline: none;
        }

        .box img {
            position: absolute;
            top: 8px;
            right: 0px;
            width: 24px;
        }
    </style>
</head>

<body>
    <div class="box">
        <label for="">
            <img src="images/close.png" alt="" id="eye">
        </label>
        <input type="password" id="pwd">
    </div>
    <script>
        // 1.获取元素
        var eye = document.getElementById('eye');
        var pwd = document.getElementById('pwd');
        // 2.注册事件
        var flag = 0;
        eye.onclick = function () {
            if (flag == 0) {
                pwd.type = 'text';
                eye.src = 'images/open.png';
                flag = 1;
            } else {
                pwd.type = 'password';
                eye.src = 'images/close.png';
                flag = 0;
            }

        }
    </script>
</body>
```

#### 样式属性操作

我们可以通过 JS 修改元素的大小、颜色、位置等样式。

常用方式：

1. element.style	行内样式操作
2. element.className    类名样式操作

##### 方式1：通过操作style属性

> 元素对象的style属性也是一个对象！
>
> 元素对象.style.样式属性 = 值;

注意：

1. JS里面的样式采取驼峰命名法，比如fontSize、backgroundColor
2. JS修改style样式操作，产生的是行内样式，CSS权重比较高

**案例代码**

```js
<body>
    <div></div>
    <script>
        // 1. 获取元素
        var div = document.querySelector('div');
        // 2. 注册事件 处理程序
        div.onclick = function() {
            // div.style里面的属性 采取驼峰命名法 
            this.style.backgroundColor = 'purple';
            this.style.width = '250px';
        }
    </script>
</body>
```

##### 案例：淘宝点击关闭二维码

![淘宝点击关闭二维码1](C:\Users\Administrator\Desktop\WebNote\第三部分 JavaScript网络编程\images\淘宝点击关闭二维码1.png)

![淘宝点击关闭二维码2](C:\Users\Administrator\Desktop\WebNote\第三部分 JavaScript网络编程\images\淘宝点击关闭二维码2.png)

```js
    <style>
        * {
            margin: 0;
            padding: 0;
        }

        .box {
            margin: 100px auto;
            width: 80px;
            position: relative;
        }

        .box h4 {
            text-align: center;
            font-size: 14px;
            font-weight: 400;
            color: chocolate;
        }

        .box img {
            width: 80px;

        }

        .box i {
            top: 19px;
            left: -17px;
            position: absolute;
            font-style: normal;
            width: 15px;
            height: 15px;
            line-height: 15px;
            text-align: center;
            border: 1px solid #ccc;
            color: #ccc;
            cursor: pointer;
        }
    </style>
</head>

<body>
    <div class="box">
        <h4>手机淘宝</h4>
        <img src="images/tao.png">
        <i class="close-btn">x</i>
    </div>
    <script>
        // 1.获取元素
        var box = document.querySelector('.box');
        var btn = document.querySelector('.close-btn');
        // 2.注册事件
        btn.onclick = function() {
            box.style.display = 'none';
        }
    </script>
</body>
```

##### 案例：循环精灵图背景

![](C:\Users\Administrator\Desktop\WebNote\第三部分 JavaScript网络编程\images\循环精灵图背景1.png)

![](C:\Users\Administrator\Desktop\WebNote\第三部分 JavaScript网络编程\images\循环精灵图背景2.png)

```js
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        
        li {
            list-style-type: none;
        }
        
        .box {
            width: 250px;
            margin: 100px auto;
        }
        
        .box li {
            float: left;
            width: 24px;
            height: 24px;
            background-color: pink;
            margin: 15px;
            background: url(images/sprite.png) no-repeat;
        }
    </style>
</head>

<body>
    <div class="box">
        <ul>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
        </ul>
    </div>
    <script>
        // 1. 获取元素 所有的小li 
        var lis = document.querySelectorAll('li');
        for (var i = 0; i < lis.length; i++) {
            // 让索引号 乘以 44 就是每个li 的背景y坐标  index就是我们的y坐标
            var index = i * 44;
            lis[i].style.backgroundPosition = '0 -' + index + 'px';
        }
    </script>
</body>
```

##### 案例：显示隐藏文本框内容

![](C:\Users\Administrator\Desktop\WebNote\第三部分 JavaScript网络编程\images\显示隐藏文本框内容1.png)

![](C:\Users\Administrator\Desktop\WebNote\第三部分 JavaScript网络编程\images\显示隐藏文本框内容2.png)

```js
    <style>
        input {
            color: #999;
        }
    </style>
</head>

<body>
    <input type="text" value="手机">
    <script>
        // 1.获取元素
        var text = document.querySelector('input');
        // 2.注册事件 获得焦点事件 onfocus 
        text.onfocus = function() {
                // console.log('得到了焦点');
                if (this.value === '手机') {
                    this.value = '';
                }
                // 获得焦点需要把文本框里面的文字颜色变黑
                this.style.color = '#333';
            }
            // 3. 注册事件 失去焦点事件 onblur
        text.onblur = function() {
            // console.log('失去了焦点');
            if (this.value === '') {
                this.value = '手机';
            }
            // 失去焦点需要把文本框里面的文字颜色变浅色
            this.style.color = '#999';
        }
    </script>

</body>
```

##### 方式2：通过操作className属性

```js
元素对象.className = 值;
因为class是关键字，所以使用className。

注意：
1.如果样式修改较多，可以采取操作类名方式更改元素样式
2.class因为是个保留字，因此使用className来操作元素类名属性
3.className会直接更改元素的类名，会覆盖原先的类名
```

**案例代码**

```js
<body>
    <div class="first">文本</div>
    <script>
        // 1. 使用 element.style 获得修改元素样式  如果样式比较少 或者 功能简单的情况下使用
        var test = document.querySelector('div');
        test.onclick = function() {
            // this.style.backgroundColor = 'purple';
            // this.style.color = '#fff';
            // this.style.fontSize = '25px';
            // this.style.marginTop = '100px';

            // 2. 我们可以通过 修改元素的className更改元素的样式 适合于样式较多或者功能复杂的情况
            // 3. 如果想要保留原先的类名，我们可以这么做 多类名选择器
            // this.className = 'change';
            this.className = 'first change';
        }
    </script>
</body>
```

##### 案例：密码框格式提示错误信息

![](C:\Users\Administrator\Desktop\WebNote\第三部分 JavaScript网络编程\images\密码框格式提示错误信息1.png)

![](C:\Users\Administrator\Desktop\WebNote\第三部分 JavaScript网络编程\images\密码框格式提示错误信息2.png)

```js
    <style>
        div {
            width: 600px;
            margin: 100px auto;
        }
        
        .message {
            display: inline-block;
            font-size: 12px;
            color: #999;
            background: url(images/mess.png) no-repeat left center;
            padding-left: 20px;
        }
        
        .wrong {
            color: red;
            background-image: url(images/wrong.png);
        }
        
        .right {
            color: green;
            background-image: url(images/right.png);
        }
    </style>
</head>

<body>
    <div class="register">
        <input type="password" class="ipt">
        <p class="message">请输入6~16位密码</p>
    </div>
    <script>
        // 首先判断的事件是表单失去焦点 onblur
        // 如果输入正确则提示正确的信息颜色为绿色小图标变化
        // 如果输入不是6到16位，则提示错误信息颜色为红色 小图标变化
        // 因为里面变化样式较多，我们采取className修改样式
        // 1.获取元素
        var ipt = document.querySelector('.ipt');
        var message = document.querySelector('.message');
        //2. 注册事件 失去焦点
        ipt.onblur = function() {
            // 根据表单里面值的长度 ipt.value.length
            if (this.value.length < 6 || this.value.length > 16) {
                // console.log('错误');
                message.className = 'message wrong';
                message.innerHTML = '您输入的位数不对要求6~16位';
            } else {
                message.className = 'message right';
                message.innerHTML = '您输入的正确';
            }
        }
    </script>
</body>
```

### 排他操作

如果有同一组元素，我们想要某一个元素实现某种样式， 需要用到循环的排他思想算法：

1. 所有元素全部清除样式（干掉其他人）

2. 给当前元素设置样式 （留下我自己）

3. 注意顺序不能颠倒，首先干掉其他人，再设置自己

```js
    <button>按钮1</button>
    <button>按钮2</button>
    <button>按钮3</button>
    <button>按钮4</button>
    <button>按钮5</button>
    <script>
        // 1. 获取所有按钮元素
        var btns = document.getElementsByTagName('button');
        // btns得到的是伪数组  里面的每一个元素 btns[i]
        for (var i = 0; i < btns.length; i++) {
            btns[i].onclick = function() {
                // (1) 我们先把所有的按钮背景颜色去掉  干掉所有人
                for (var i = 0; i < btns.length; i++) {
                    btns[i].style.backgroundColor = '';
                }
                // (2) 然后才让当前的元素背景颜色为pink 留下我自己
                this.style.backgroundColor = 'pink';

            }
        }
    </script>
```

#### 案例：百度换肤

![](C:\Users\Administrator\Desktop\WebNote\第三部分 JavaScript网络编程\images\百度换肤(1).png)

![](C:\Users\Administrator\Desktop\WebNote\第三部分 JavaScript网络编程\images\百度换肤(2).png)

```js
   <style>
        * {
            margin: 0;
            padding: 0;
        }
        
        body {
            background: url(images/1.jpg) no-repeat center top;
        }
        
        li {
            list-style: none;
        }
        
        .baidu {
            overflow: hidden;
            margin: 100px auto;
            background-color: #fff;
            width: 410px;
            padding-top: 3px;
        }
        
        .baidu li {
            float: left;
            margin: 0 1px;
            cursor: pointer;
        }
        
        .baidu img {
            width: 100px;
        }
    </style>
</head>

<body>
    <ul class="baidu">
        <li><img src="images/1.jpg"></li>
        <li><img src="images/2.jpg"></li>
        <li><img src="images/3.jpg"></li>
        <li><img src="images/4.jpg"></li>
    </ul>
    <script>
        // 1. 获取元素 
        var imgs = document.querySelector('.baidu').querySelectorAll('img');
        // console.log(imgs);
        // 2. 循环注册事件 
        for (var i = 0; i < imgs.length; i++) {
            imgs[i].onclick = function() {
                // this.src 就是我们点击图片的路径   images/2.jpg
                // console.log(this.src);
                // 把这个路径 this.src 给body 就可以了
                document.body.style.backgroundImage = 'url(' + this.src + ')';
            }
        }
    </script>
</body>
```

#### 案例：表格隔行变色

![](C:\Users\Administrator\Desktop\WebNote\第三部分 JavaScript网络编程\images\表格隔行变色 (1).png)

![](C:\Users\Administrator\Desktop\WebNote\第三部分 JavaScript网络编程\images\表格隔行变色 (2).png)

# JavaScript高级

## 面向过程与面向对象

### 面向过程

- 面向过程就是分析出解决问题所需要的步骤，然后用函数把这些步骤一步一步实现，使用的时候再一个一个的依次调用就可以了。

### 面向对象

- 面向对象是把事务分解成为一个个对象，然后由对象之间分工与合作。

### 面向过程与面向对象对比

|      | 面向过程                                                     | 面向对象                                                     |
| ---- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 优点 | 性能比面向对象高，适合跟硬件联系很紧密的东西，例如单片机就采用的面向过程编程。 | 易维护、易复用、易扩展，由于面向对象有封装、继承、多态性的特性，可以设计出低耦合的系统，使系统 更加灵活、更加易于维护 |
| 缺点 | 不易维护、不易复用、不易扩展                                 |                                                              |

## 对象与类

### 对象

对象是由属性和方法组成的：是一个无序键值对的集合,指的是一个具体的事物

- 属性：事物的特征，在对象中用属性来表示（常用名词）
- 方法：事物的行为，在对象中用方法来表示（常用动词）

#### 创建对象

```js
//以下代码是对对象的复习
//字面量创建对象
var ldh = {
    name: '刘德华',
    age: 18
}
console.log(ldh);

//构造函数创建对象
  function Star(name, age) {
    this.name = name;
    this.age = age;
 }
var ldh = new Star('刘德华', 18)//实例化对象
console.log(ldh);	
```

### 类

​		在 ES6 中新增加了类的概念，可以使用 class 关键字声明一个类，之后以这个类来实例化对象。类抽象了对象的公共部分，它泛指某一大类（class），对象特指某一个，通过类实例化一个具体的对象

#### 创建类

1. 语法:

```js
//步骤1 使用class关键字
class name {
  // class body
}     
//步骤2使用定义的类创建实例  注意new关键字
var xx = new name();     
```

2. 示例

```js
 // 1. 创建类 class  创建一个 明星类
 class Star {
   // 类的共有属性放到 constructor 里面
   constructor(name, age) {
   this.name = name;
   this.age = age;
   }
 }
   // 2. 利用类创建对象 new
   var ldh = new Star('刘德华', 18);
   console.log(ldh);
```

#### 类创建添加属性和方法

```js
// 1.通过class创建一个类
class Star {
    //类的共有属性放到constructor里面，构造器或者构造函数
    constructor(uname, age) {
        this.uname = uname;
        this.age = age;
    }
    
    sing(song) {
        console.log(this.uname + '唱' + song);
    }
}
// 2.利用类创建对象 new
var ldh = new Star('刘德华', 18);
console.log(ldh);// Star{uname: "刘德华", age: 18}
ldh.sing('冰雨');// 刘德华唱冰雨
```

**注意哟:**

1. 通过class 关键字创建类, 类名我们还是习惯性定义首字母大写
2. 类里面有个constructor 函数,可以接受传递过来的参数,同时返回实例对象
3. constructor 函数 只要 new 生成实例时,就会自动调用这个函数, 如果我们不写这个函数,类也会自动生成这个函数
4. 多个函数方法之间不需要添加逗号分隔
5. 生成实例 new 不能省略
6. 语法规范, 创建类 类名后面不要加小括号,生成实例 类名后面加小括号, 构造函数不需要加function

#### 类的继承

1. 语法

```js
// 父类
class Father{   
} 

// 子类继承父类
class  Son  extends Father {  
}       
```

2. 示例

```js
class Father {
      constructor(surname) {
        this.surname= surname;
      }
      say() {
        console.log('你的姓是' + this.surname);
       }
}

class Son extends Father{  // 这样子类就继承了父类的属性和方法
}
var damao= new Son('刘');
damao.say();      //结果为 你的姓是刘
```

- 子类使用super关键字访问父类的方法

  ```js
  //定义了父类
  class Father {
     constructor(x, y) {
     this.x = x;
     this.y = y;
     }
     sum() {
     console.log(this.x + this.y);
  	}
   }
  //子元素继承父类
      class Son extends Father {
     		 constructor(x, y) {
      		super(x, y); //使用super调用了父类中的构造函数
      	}
      }
      var son = new Son(1, 2);
      son.sum(); //结果为3
  ```

  **注意:** 

  1. 继承中,如果实例化子类输出一个方法,先看子类有没有这个方法,如果有就先执行子类的

  2. 继承中,如果子类里面没有,就去查找父类有没有这个方法,如果有,就执行父类的这个方法(就近原则)

  3. 如果子类想要继承父类的方法,同时在自己内部扩展自己的方法,利用super 调用父类的构造函数,super 必须在子类this之前调用

     ```js
      // 父类有加法方法
      class Father {
        constructor(x, y) {
        this.x = x;
        this.y = y;
        }
        sum() {
        console.log(this.x + this.y);
        }
      }
      // 子类继承父类加法方法 同时 扩展减法方法
      class Son extends Father {
        constructor(x, y) {
        // 利用super 调用父类的构造函数 super 必须在子类this之前调用,放到this之后会报错
        super(x, y);
        this.x = x;
        this.y = y;
     
       }
       subtract() {
       console.log(this.x - this.y);
       }
     }
     var son = new Son(5, 3);
     son.subtract(); //2
     son.sum();//8
     ```

  4. 时刻注意this的指向问题,类里面的共有的属性和方法一定要加this使用.

     1. constructor中的this指向的是new出来的实例对象 
     2. 自定义的方法,一般也指向的new出来的实例对象
     3. 绑定事件之后this指向的就是触发事件的事件源

  5. 在 ES6 中类没有变量提升，所以必须先定义类，才能通过类实例化对象

### 面向对象案例：tab栏切换


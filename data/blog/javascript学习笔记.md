---
title: javascript学习笔记
date: '2023-04-18'
tags: ['javascript']
summary:
---

# javascript 学习笔记

```js
1. JS中每一个语句都应该以分号结尾
    - 在js中有自动添加分号机制，所以即使不写也不会报错
2. JS中严格区分大小写
3. JS会忽略多个空格和换行，所以可以通过空格和换行来对代码进行格式化
```

# day01

## Overview

A post on the new features introduced in v1.0. New features:

<TOCInline toc={props.toc} exclude="Overview" toHeading={2} />

## 04\_字面量和变量

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>字面量和变量</title>
    <script>
      /*
            字面量
                - 字面量就表示的是一个值，它所表示的意思就是它的字面意思
                - 比如：1, 2, 3 'hello' true ....
                - 字面量可以在js中直接使用，但是通常不会这这么做

            变量
                - 变量可以用来存储字面量，一个变量可以存储任意类型的字面量
                - 我们一般都是通过变量去存储字面量而不是直接使用字面量

                - 变量的使用：
                    声明变量：
                        - 使用let关键字来声明变量
                            let a;
                            let b, c, d;
                    为变量赋值：
                        a = xxx;
                        b = xxx;

               - 声明和赋值同时进行：
                let a = xxx;
                let b = xxx, c = yyy ;
        */

      // alert(123423543525);

      // 创建一个变量
      let a
      // 为变量赋值
      a = '哈哈'
      a = 33

      // 声明和赋值同时进行
      let age = 33

      // alert(age);

      /*
            const 用来声明一个常量，常量只能进行一次赋值无法修改
        */
      const b = 44
      // b = 33; // b为常量，无法赋值

      alert(b)
    </script>
  </head>
  <body></body>
</html>
```

## 05\_标识符

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>标识符</title>
    <script>
      /*
       *   标识符
       *       - 在程序中所有的可以自主命名的内容都可以认为是标识符
       *           - 比如：变量名、函数名、类名...
       *       - 标识符需要遵循如下规范：
       *           1. 标识符中可以含有字母、数字、_、$，但是不能以数字开头
       *           2. 标识符不能是JS中的关键字和保留字，也不建议使用js中内置函数名和变量名
       *               https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Lexical_grammar
       *           3. 标识符应该要遵循驼峰命名法
       *               - 驼峰命名法：
       *                   首字母小写，每个单词开头字母大写
       *                       maxlength  --> maxLength
       *                       xxxyyyzzz --> xxxYyyZzz
       * */
      let a = 10
      let b = 20
      let ab123_$ = 33
      // let as@!#!@#!;
      // let var = 33;
      // let alert = 44; 不要这么用
      // alert(123);
      let maxLength = 153
    </script>
  </head>
  <body></body>
</html>
```

## 06\_数据类型

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>数据类型</title>
    <script>
      /*
       *   数据类型 （值的类型）
       *       字符串（string）
       *           - js中的字符串需要使用引号引起来
       *           - 双引号或单引号都行但是不能混合使用
       *           - 引号不能跨行使用，同类型的引号不能嵌套
       *           - js中使用 \ 作为转义字符
       *               \' 表示 '
       *               \" 表示 "
       *               \n 表示 换行
       *               \t 表示 制表符
       *               \\ 表示 \
       *
       *
       * */

      let str = 'hello'
      str = 'hi'
      str = 'hi'

      str = 'hello hello how are you'

      str = "I'm Jack"
      str = "I'm \n Jack"
      str = "I'm\tJack"

      // console.log(str);

      // document.write('哈哈<br>嘻嘻');
      // console.log('哈哈\n嘻嘻');

      //         str = 'HELLO \
      // HELLO';

      // alert(str);
    </script>
  </head>
  <body></body>
</html>
```

## 07\_模板字符串

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>模板字符串</title>
    <script>
      /*
       *   模板字符串（老版本的浏览器不支持）
       *       - 使用反单引号 ` 来创建模板字符串
       *       - 特点：
       *           1.可以换行，并保留字符串中的格式
       *           2.在模板字符串中可以直接嵌入变量
       *               变量的语法 ${变量}
       * */
      let str = `hello
        hello
        hello
        hello`

      // alert(str);

      let name = '石天凯'
      str = `我好喜欢${name}, 因为他好帅！`

      alert(str)
    </script>
  </head>
  <body></body>
</html>
```

## 08\_数值

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>数值</title>
    <script>
      /*
            在JS中，所有数值包含整数和浮点数(小数)都属于number类型
                - 在JS中可以确保大部分的整数运算得到一个精确的结果
                - 在JS中，小数运算有可能得到一个不精确的结果
                    所以，在JS中不要直接对精度要求高的运算（尤其是涉及到钱的）
                - 当数值超过一定范围后，会使用 Infinity 来表示
                    Infinity 表示正无穷
                - NaN也是一个特殊数字，表示 Not a Number 非法数字
        */
      let num1 = 10
      let num2 = 3.5
      let str = '10'
      let num3 = 123214325434541412314131231231233112312312 + 10
      let num4 = 0.1 + 0.2
      let num5 =
        123214325434541412314131231231233112312312 ** 123214325434541412314131231231233112312312
      let num6 = Infinity
      let num7 = 10 - 'hello'
      let num8 = NaN

      // console.log(typeof num8);

      // alert(num1);
      // alert(str);

      /*
       *   typeof运算符
       *      - 用来检查一个值的类型
       *      - 使用typeof检查一个字符串时，会返回 string
       *           检查一个数值时，它会返回 number
       * */
      // console.log(typeof str);

      /*
       *   其他进制的数字：
       *       二进制 0b开头
       *       八进制 0o开头
       *       十六进制 0x开头
       * */

      let num9 = 0b10 // 二进制
      num9 = 0o10 // 八进制
      num9 = 0xff // 十六进制

      // console.log(num9);

      /*
       *   在ES2020最新标准中，提供了一个新数字类型bigint 表示大整数（了解）
       * */
      let num10 = 100n

      console.log(num10 + 10n)
      // console.log(typeof num10);
    </script>
  </head>
  <body></body>
</html>
```

## 09\_布尔值

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>布尔值</title>
    <script>
      /*
       *   布尔值（boolean）
       *      - 布尔值用来进行逻辑判断
       *      - 布尔值只有两个：
       *           true  真
       *           false 假
       *
       *       - 使用typeof检查一个布尔值会返回boolean
       * */

      let bool = true
      bool = false

      alert(typeof bool)
    </script>
  </head>
  <body></body>
</html>
```

## 10\_空值和未定义

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>空值和未定义</title>
    <script>
      /*
       *   null 通常用来表示一个空的对象，一个不存在的东西
       *       null类型只有一个值 就是 null
       *       - 使用typeof检查一个null时，它会返回 'object'
       *
       *   undefined 表示未定义，当我们定义一个变量但是不赋值时它就是undefined
       *       undefined类型的值只有一个，就是undefined
       *       - 使用typeof检查一个undefined时，会返回'undefined'
       *
       *
       *  基本数据类型：
       *   - 基本数据类型是构成整个js世界的基石
       *       数值（number）
       *       字符串（string）
       *       布尔值（boolean）
       *       空值（null）
       *       未定义（undefined）
       *       - 在JS中所有的基本类型都是不可变类型，
       *           值一旦创建，就不可修改！
       *
       *   - JS中的变量并不直接存储，而是存储值的内存地址
       *       当我们访问变量时，是通过地址找到其对应的值
       *
       *   - 所以JS中的变量，其实更像是一个值的别名
       *
       *  预习：
       *   类型转换
       *   运算符
       *   流程控制语句
       *
       * */
      let a = null
      let b = undefined // 不要这么做
      let c = 100

      console.log(c) // 100
    </script>
  </head>
  <body></body>
</html>
```

# day02

## 11\_类型转换

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
            类型转换，指将其他的数据类型转换string、number、boolean

            将其他的类型转换为字符串
                方式一：
                    调用被转换类型的toString()方法
                    - 调用xxx的yyy方法 ---> xxx.yyy()
                    - 由于null和undefined中不含有toString()方法
                        所以对它俩调用时会报错

                方式二：
                    调用String()函数，来将被转换类型转换为字符串
                    - 调用xxx函数 ---> xxx()
                    - 原理：
                        对于具有toString()方法的值，就是直接调用toString()对其进行转换，
                        但是对于null来说，它是直接将其转换为 'null'
                        undefined 直接转换为 'undefined'



        */
      let a = 10
      a = NaN // NaN --> 'NaN'
      a = true // true --> 'true'

      a = 33

      a = null
      a = undefined

      console.log(a, typeof a)

      // 调用toString()，将10转换为字符串
      // a = a.toString();
      // 调用String()函数来将其他类型转换为字符串
      a = String(a)

      console.log(a, typeof a)
    </script>
  </head>
  <body></body>
</html>
```

## 12\_其他类型转换为数字

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   使用Number()函数来将一个其他类型转换为数字
       *       转换的情况：
       *           字符串：
       *               如果字符串是一个合法数字，则直接转换为对应的数字
       *               如果字符串不是一个合法数字，则转换为NaN
       *           布尔值
       *               true --> 1
       *               false --> 0
       *           null --> 0
       *           undefined --> NaN
       *
       *   除了Number()以外，
       *   还有两个函数是专门用来将一个字符串转换为数字的
       *       parseInt()
       *           - 将一个字符串解析为一个整数
       *           - 该函数会自左向右依次读取一个字符串中的字符，
       *               直到找到字符串中所有的合法整数为止
       *           - 还可以用来对一个数字进行取整
       *       parseFloat()
       *           - 将一个字符串解析为一个小数
       * */
      let a = '123' // 123
      a = '3.14' // 3.14
      a = 'abc' // NaN
      a = '0xff' // 255
      a = 'Infinity' // Infinity
      a = '123px' // NaN
      a = true // 1
      a = false // 0
      a = null // 0
      // a = undefined; // NaN
      console.log(a, typeof a)

      a = Number(a)
      console.log(a, typeof a)

      let b = '123px'
      b = '123.45px12312312312312fdfdsfs'
      b = 333.456
      // b = true;
      console.log(b, typeof b)

      // b = parseInt(b);
      // b = parseFloat(b);
      b = parseInt(b)
      console.log(b, typeof b)
    </script>
  </head>
  <body></body>
</html>
```

## 13\_其他类型转换为布尔值

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   使用Boolean()函数来将其他类型转换为布尔值
       *       - 所有表示没有或错误的都会转换为false
       *       - 对于数值：
       *              除了0和NaN，都是true
       *       - 对于字符串：
       *              空串是false，其他都是true
       *       - null和undefined都是false
       *       - 一般情况对象都会转换为true
       *
       *       - false的情况
       *           0、NaN、''、false、null、undefined
       * */

      let a = 10 // true
      a = -44 // true
      a = 0 // false
      a = NaN // false
      a = Infinity // true

      a = 'Hello' // true
      a = 'false' // true
      a = '   ' // true;
      a = '' // false
      a = null // false
      a = undefined // false

      console.log(a, typeof a)

      a = Boolean(a)
      console.log(a, typeof a)
    </script>
  </head>
  <body></body>
</html>
```

## 14\_运算符

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   运算符（操作符）
       *       - 通过运算符可以对一个值或多个值进行各种运算
       *       - 对一个值进行运算的运算符，称为一元运算符
       *           对两个值进行运算，叫做二元运算符
       *           以此类推
       *
       *       - 算术运算赋
       *           + 对两个值进行加法运算
       *           - 对两个值进行减法运算
       *           * 对两个值进行乘法运算
       *           / 对两个值进行除法运算
       *           ** （幂运算）求一个值的几次幂
       *           % （取模） 两个数相除取余数
       * */

      let result = 10 + 33
      result = 10 - 5
      result = 10 / 0 // Infinity
      result = 2 ** 10
      result = 16 ** 0.5 // 16的平方根
      result = 2 ** 0.5 // 2的平方根

      result = 10 % 2 // 0
      result = 10 % 3 // 1
      result = 10 % 4 // 2

      // 如果对于两个字符串做加法运算，则会将两个字符串拼接为一个
      result = 'hello' + '哈哈'

      //       1    +  0
      result = true + false // 1

      /*
       *   除了字符串的加法以外，对其他类型的值进行算术运算时
       *       都会转换为数值然后再进行运算
       *
       *   所以我们可以通过为一个任意值 -0，*1等方式来将其转换为数字
       *   这种方式称为隐式类型转换，它的原理和Number()函数一样，
       *   但是更简单一些
       *
       *   任何值和NaN做任何运算结果都是NaN（除了字符串加法）;
       * */

      result = 1 + true // 2
      result = 456 * null // 0

      // 33 - NaN
      result = 33 - undefined // NaN

      let a = true

      a = '123'
      // console.log(result);
      console.log(a, typeof a)

      // a = 0 + a;
      // a = a - 0;
      // a = a * 1;

      a = a + 0
      console.log(a, typeof a)
    </script>
  </head>
  <body></body>
</html>
```

## 15\_字符串的加法

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   任何值和字符串做加法时都会转换为字符串
       *       然后再和字符串进行拼串
       *
       *   利用这个特点，可以通过为一个任意值 加上一个空串('')的形式
       *       来将其转换为字符串，它的原理和String()函数是一样的
       *       但是这种方式要简单一些
       * */
      // 'hello' + '123' = 'hello123'
      let a = 'hello' + 123
      a = 'hello' + NaN
      a = 1 + '2' + 3 // '123'

      // a = true;
      // console.log(a, typeof a);
      // a = a + '';
      // console.log(a, typeof a);

      let b = 340
      b = 45

      console.log('b = ' + b)
      console.log('b =', b)
      console.log(`b = ${b}`)
    </script>
  </head>
  <body></body>
</html>
```

##

## 16\_一元的运算

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>一元运算</title>
    <script>
      let a = 10
      a = 'hello'
      a = 0
      a = true
      a = false
      a = null
      a = undefined
      a = '123.56px'
      //a=parseInt(a);
      //a=parseFloat(a);
      a = +a
      console.log('a=' + a)
    </script>
  </head>
  <body></body>
</html>
```

## 17\_一元运算符

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   typeof
       *       - 检查一个值的类型
       *   +
       *       - 一元的+（正号）
       *       - 不会对数值产生任何影响
       *   -
       *       - 一元的-（负号）
       *       - 会对数值进行符号位取反
       *
       *   - 对于非数值类型的值进行正负运算时
       *       它会先将其转换位数值然后再运算
       *
       *   - 利用一元的+，可以将一个任意类型的值转换位数值，
       *       原理同Number()函数，但是更加的简单
       * */

      let a = 10
      a = +a

      a = true

      // console.log(a, typeof a);

      // a = -a;
      a = +a
      // console.log('a =', a, typeof a);

      a = 1 + +'2' + 3
      console.log(a)
    </script>
  </head>
  <body></body>
</html>
```

## 18\_自增和自减

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   自增（++）
       *       - 自增分为前++（++a） 和 后++（a++）
       *       - 无论是++a还是a++，对于a来说都是一样的
       *           都会使变量a立刻增加1
       *       - a++和++a的返回结果不同
       *           a++ 返回的是变量自增前的值，旧值
       *           ++a 返回的是变量自增后的值，新值
       *
       *
       * */

      let a = 10

      // ++a;
      // console.log('++a =', ++a); // 11
      // console.log('a++ =', a++); // 11
      // console.log('a =', a); // 12

      // a = 10
      // a = a++;
      // console.log('a =', a);

      a = 10
      //          10  + 12 + 12
      let result = a++ + ++a + a
      // console.log('result =', result);

      a = 10
      /*
       *
       * 自减（--）
       *   - 自减分为前--(--a) 和后--(a--)
       *   - 无论是--a还是a--都会使变量a立刻自减1
       *   - 不同点在于 --a 和 a--的值不同
       *        --a是自减后的值，新值
       *        a--是自减前的值，旧值
       *
       * */

      // a--;
      // --a;

      // console.log('a-- =', a--);
      // console.log('--a =', --a);
      // console.log('a =', a);

      let n,
        n1 = 20,
        n2 = 20

      n = n1++
      console.log('n =', n) // 20
      console.log('n1 =', n1) // 21

      n = ++n1
      console.log('n =', n) // 22
      console.log('n1 =', n1) // 22

      n = n2--
      console.log('n =', n) // 20
      console.log('n2 =', n2) // 19

      n = --n2
      console.log('n =', n) // 18
      console.log('n2 =', n2) // 18
    </script>
  </head>
  <body></body>
</html>
```

## 19\_赋值运算符

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   赋值运算符
       *       - 用来将一个值赋值给一个变量
       *           =
       *               - =号用于将符号右侧的值赋值给左侧的变量
       *           +=
       *               - a += x 等价于 a = a + x
       *           -=
       *               - a -= x 等价于 a = a - x
       *           *=
       *               - a *= x 等价于 a = a * x
       *           /=
       *               - a /= x 等价于 a = a / x
       *           **=
       *               - a **= x 等价于 a = a ** x
       *           %=
       *               - a %= x 等价于 a = a % x
       *
       *
       *   哪些情况会导致变量发生变化（为变量进行重新赋值）：
       *       1. 对变量使用赋值运算符
       *           a = xx
       *           a += xx
       *           a -= xx
       *           ...
       *       2. 对变量使用自增自减
       *           a++
       *           ++a
       *           a--
       *           --a
       *
       * */

      let a = 10
      // let b = a;

      a += 5 // a = a + 5;

      console.log('a =', a)
    </script>
  </head>
  <body></body>
</html>
```

## 20\_逻辑运算符

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   逻辑运算符
       *       ! 逻辑非
       *           - !可以对一个值进行非运算（取反操作）
       *           - 如果值是true，则变成false，false变成true
       *           - 如果对一个非布尔值进行逻辑非运算，
       *               它会先将其转换为布尔值，然后再取反
       *
       *           - 利用这一点，可以对一个任意值，
       *               取两次反来将其转换为布尔值
       *               原理和Boolean()函数一样
       *
       *       &&  逻辑与
       *       ||  逻辑或
       * */

      let bool = false
      bool = !bool
      // console.log('bool =', bool);

      let num = 10

      num = !!num
      // console.log(num, typeof num)

      /*
       *
       *  &&  逻辑与
       *       - 可以对符号左右两侧的值进行与运算
       *       - 如果两侧的值都是true，则返回true，否则返回false
       *       - 与运算是找false的
       *       - 与运算是短路的与
       *           如果第一个值是否false，则不会去看第二个值
       *
       *  ||  逻辑或
       *       - 可以对符号两侧的值进行或运算符
       *       - 如果两侧有一个true，就返回true，否则返回false
       *       - 或运算是找true
       *       - 或运算是短路的或
       *           如果第一个值是true，则不会看第二个值
       * */

      let result = true && true // true
      result = true && false // false
      result = false && true // false
      result = false && false // false

      // console.log('result =', result)

      // true && alert('你猜我出来吗？'); // 第一个值是true，会看第二个值
      // false && alert('你猜我出来吗？'); // 第一个值是false，不会看第二个值

      result = true || true // true
      result = true || false // true
      result = false || true // true
      result = false || false // false

      // console.log('result =', result)

      // true || alert('你猜我出来吗？'); // 第一个值是true，不看第二个
      false || alert('你猜我出来吗？') // 第一个值是false，看第二个
    </script>
  </head>
  <body></body>
</html>
```

## 21\_非布尔值的逻辑运算

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   与运算：
       *       - 如果对非布尔值进行与运算，
       *           会首先将其转换为布尔值，然后运算，最终返回原值
       *       - 如果第一个值是true，则返回第二个值
       *           如果第一个值是false，则返回第一个值
       *
       *   或运算
       *       - 如果第一个值是true，则直接返回第一个，否则返回第二个
       *
       *   与找false，或找true
       * */

      //          true && true
      let result = 'hello' && 1 // 1
      result = 1 && 'hello' // 'hello'
      // true && false
      result = 1 && NaN //NaN

      // false && true
      result = NaN && 1 //NaN

      // false && false
      result = NaN && 0 //NaN
      result = 0 && NaN //0

      result = 1 || 'hello'
      result = 1 || true
      result = 1 || NaN
      result = NaN || 'hello'
      result = NaN || 0
      result = NaN || 33

      result = '' && 123
      result = 1 && 'hello'
      result = 1 || 'hello'
      result = null || 'hello'

      console.log('result =', result)
    </script>
  </head>
  <body></body>
</html>
```

## 22\_关系运算符

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      // let a = 123;
      // 将a转换为字符串，调用toString()来转
      // a = a && a.toString();
      // console.log(a, typeof a)

      /*
       *   关系运算符，用来比较两个值之间的大小等于的关系
       *       使用关系运算符时，如果关系成立则返回true，不成立则返回false
       *   >
       *       - 比较左侧值是否大于右侧值
       *   >=
       *       - 比较左侧值是否大于或等于右侧值
       *   <
       *       - 比较左侧值是否小于右侧值
       *   <=
       *       - 比较左侧值是否小于或等于右侧值
       * */

      let result = 10 > 5 // true
      result = 10 > 10 // false
      result = 10 >= 10 // true
      result = 10 >= 7 // true
      result = 10 >= 17 // false

      /*
       *   对于非数值类型的值进行大于小于的比较时，
       *       浏览器会自动将其转换为数字然后再比较
       *
       *   注意，如果比较的是两个字符串的大小，则情况比较特殊，这是为什么呢？
       * */
      //  1   >  0
      result = true > false // true
      result = 10 < '55' // true
      result = 10 < '5' // false
      result = true < '5' // true
      result = null < '5' // true
      // 任何值和NaN作比较最后结果都是false
      result = null <= undefined // false
      console.log('result =', result)
      5
    </script>
  </head>
  <body></body>
</html>
```

# day03

## 23\_关系运算符

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      let result = true > false

      result = '5' > '10' // true

      /*
       *   特殊情况：
       *       - 当比较运算符的两侧都是字符串时，它不会将其转换为数字进行比较
       *           而是逐位比较字符串的字符编码，
       *           利用这个特点可以对一个字符串按照字母顺序进行排序
       * */

      //       97     98
      result = 'a' < 'b' // true

      //          99 < 98
      result = 'c' < 'b' // false

      result = 'c' < 'background' // false

      //      30    34
      result = '1' < '5' // true
      result = '10' < '5' // true

      let a = '10'
      let b = '5'

      // console.log('result =', result);

      console.log(+a < b)
    </script>
  </head>
  <body></body>
</html>
```

## 24\_相等和全等

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   相等运算符
       *       ==
       *           - 相等运算符用来比较两个值是否相等
       *           - 相等运算符会对值进行自动的类型转换，
       *               如果比较的两个值的类型不同，会将其转换为相同的类型然后再比较
       *               通常情况下，不同类型都会转换为Number然后再比较
       *               null 和 undefined 做相等比较时，会返回true
       *
       *       === （全等）
       *           - 全等用来检查两个值是否全等
       *           - 全等运算不会发生自动的类型转换，
       *               如果两个值的类型不同，直接返回false
       *           - null和undefined做全等比较时，返回false
       *
       *       != (不相等)
       *           - 比较两个值是否不相等
       *           - 如果不相等返回true，相等返回false
       *           - 会做自动类型转换，将两个值转换为相同的类型然后再比较
       *
       *
       *       !== (不全等)
       *           - 比较两个值是否不全等
       *           - 如果不全等返回true，全等返回false
       *           - 不会做自动的类型转换，如果两个值的类型不同，直接返回true
       *
       * */

      // console.log(10 == 10); // true
      // console.log(10 == "10"); // true
      // console.log(true == "1"); // true
      // console.log(true == "true"); // false
      // console.log(null == 0); // false
      // console.log(null == undefined); // true
      // console.log(null >= 0); // false

      // console.log(10 === '10'); // false
      // console.log(true === '1'); // false
      // console.log(null === undefined); // false

      // NaN不和任何值相等，包括它自己
      // console.log(NaN == NaN);
      // console.log(NaN === NaN);

      let a = NaN

      // 检查一个值是否是NaN时，需要使用函数 isNaN()
      // console.log(isNaN(a));

      console.log(10 != '10')
    </script>
  </head>
  <body></body>
</html>
```

## 25\_条件运算符

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   条件运算符（三元运算符，三目运算符）
       *       - 语法：
       *           条件表达式 ? 语句1 : 语句2
       *
       *       - 执行流程：
       *           条件运算符在执行时，会先对条件表达式进行求值判断，
       *               如果判断结果为true，则执行语句1
       *               如果判断结果为false，则执行语句2
       * */

      // false ? alert('语句1') : alert('语句2');
      let num = 30
      // num > 20 ? alert('num比20大！') : alert('num比20小！');

      let a = 140
      let b = 330
      let c = 55

      // let max = a > b ? a : b;
      // max = max > c ? max : c;

      let max = a > b ? (a > c ? a : c) : b > c ? b : c

      console.log('max =', max)
    </script>
  </head>
  <body></body>
</html>
```

## 26\_运算符的优先级

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   和数学运算一样，JS中运算符也有优先级的问题
       *       比如：先乘除后加减
       *
       *   运算符的优先级根据运算符优先级表来决定
       *       在表中，位置越考上的优先级越高，优先级越高越优先计算
       *       优先级一样，按照从左向右的顺序依次计算
       *   https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence
       *
       *       优先级的表不需要记忆，遇到优先级不清的，可以通过()来改变优先级
       * */
      let result = (1 + 2) * 3
      result = (1 || 2) && 3

      let a = null

      a?.toString()
    </script>
  </head>
  <body></body>
</html>
```

## 27\_代码块

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>代码块</title>
    <script>
      /*
       *   在JS中我们使用{}来为代码进行分组,
       *       一对大括号就是一个代码块，
       *       同一代码块中的代码要么都执行，要么都不执行
       *       代码块中使用let声明的变量，在代码块外部无法访问
       *       但是 使用var 声明的变量没有块作用域，在代码块的外部也可以访问
       * */

      {
        var b = 33
        let a = 10
        console.log('a =', a)
      }

      console.log('b =', b)
      console.log('a =', a)

      // {
      //     let b = 30;
      //     console.log('b =', b);
      // }
    </script>
  </head>
  <body></body>
</html>
```

## 28\_流程控制语句

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>流程控制语句</title>
    <script>
      /*
       * 代码默认是按照自上向下的顺序一行一行执行的
       *   但是仅仅是这样，并不能满足我们开发的需要
       *
       * 可以通过流程控制语句来改变程序执行的顺序：
       *   条件判断语句
       *   条件分支语句
       *   循环语句
       * */

      /*
       *
       *   条件判断语句
       *
       *       语法：
       *           if(条件表达式){
       *               语句...
       *           }
       *
       *
       *       执行流程：
       *           if语句在执行时，先对条件表达式进行求值判断
       *               如果结果为true，则执行if后的语句
       *               如果结果为false，则不执行
       *
       *           if语句默认只会控制紧随其后的那条语句
       *               对于我们来说，最佳实践是，即使if后仅有一条语句，最好也使用{}
       *
       *           如果条件表达式的结果是一个非布尔值，会转换为布尔值进行判断
       *
       * */

      // if(false)
      //     alert('你猜我出来吗？');

      let a = 123
      // if(a > 20){
      //     alert('a比20大！');
      //     alert('谁也管不了我！');
      // }

      // if(a){
      //     alert('hello');
      // }

      // if(isNaN(a)){
      //     alert('a的值是NaN');
      // }

      // a >= 10 && a <= 20
    </script>
  </head>
  <body></body>
</html>
```

## 29_if 语句

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   if-else 语句
       *       if(条件表达式){
       *           语句...
       *       }else{
       *           语句...
       *       }
       *
       *   执行流程：
       *       if-else执行时，先对if后的条件表达式进行求值判断
       *           如果为true，则执行if后的语句
       *           如果为false，则执行else后的语句
       *
       *   if-else if-else语句
       *       if(条件表达式){
       *           语句..
       *       }else if(条件表达式){
       *           语句..
       *       }else if(条件表达式){
       *           语句..
       *       }else{
       *           语句..
       *       }
       *
       *   执行流程：
       *       if-else if-else语句在执行时，
       *           它会自上向下依次对if后的条件表达式进行求值判断
       *           如果判断结果为true，则执行当前if后的语句，执行完毕语句结束了
       *           如果判断结果为false，则继续向下判断，直到找到true为止。
       *           如果所有的判断结果都是false，则执行else后的语句
       *
       *           if-else if-else 语句中，只会有一个代码块执行，
       *               代码块执行后，其他语句不会再判断，语句立即结束
       * */

      let age = 66

      //判断当前年龄是否退休
      // if(age >= 60){
      //     alert('你已经退休了~~');
      // }else{
      //     alert('你还得好好干~~');
      // }

      age = 300

      // if(age >= 300){
      //     alert('活着可真累啊~');
      // }else if(age >= 80){
      //     alert('和楼上比，我还很年轻~');
      // }else if(age >= 60){
      //     alert('你已经退休了~~~');
      // }else if(age >= 30){
      //     alert('你已经中年了~~~');
      // }else if(age >= 18){
      //     alert('你已经成年了~~~');
      // }else{
      //     alert('你还是个小孩~~~');
      // }

      age = 70

      if (age >= 18 && age < 30) {
        alert('你已经成年了~~~')
      } else if (age >= 30 && age < 60) {
        alert('你已经中年了~~~')
      } else if (age >= 60) {
        alert('你已经退休了~~~')
      }
    </script>
  </head>
  <body></body>
</html>
```

## 30_if 练习

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
        * - 练习1：
            编写一个程序，获取一个用户输入的整数。然后通过程序显示这个数是奇数还是偶数。
        * */

      // prompt() 函数用来获取用户输入的内容
      //  用户输入的内容会作为函数的返回值返回，需要定义变量来接收
      //  该函数的返回值类型总是一个字符串
      let num = +prompt('请输入一个整数：')

      // alert('num = ' + num);
      // console.log(num, typeof num);
      // 判断 num 是奇数还是偶数
      if (num % 2 === 0) {
        alert(`${num}是偶数！`)
      } else {
        alert(`${num}是奇数！`)
      }
    </script>
  </head>
  <body></body>
</html>
```

## 31_if 练习

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
        *
        * - 练习2：
          编写一个程序，检查任意一个年份是否是闰年。
            如果一个年份可以被4整除不能被100整除，或者可以被400整除，这个年份就是闰年
        * */
      // 创建一个变量，表示年份
      // let year = +prompt('请输入一个年份：');
      // // 检查year是否是闰年
      // if(year % 4 === 0 && year % 100 !== 0 || year % 400 === 0){
      //     alert(`${year}是闰年！`);
      // }else{
      //     alert(`${year}是平年！`);
      // }

      /*
        *
        * - 练习3：
              我家的狗5岁了，5岁的狗相当于多大年龄的人呢？
              其实非常简单，狗的前两年每一年相当于人类的10.5岁，然后每增加一年就增加四岁。
              那么5岁的狗相等于人类的年龄就应该是10.5+10.5+4+4+4 = 33岁

          	编写一个程序，获取用户输入的狗的年龄，然后通过程序显示其相当于人类的年龄。
          	如果用户输入负数，请显示一个提示信息
        *
        * */

      // 获取狗的年龄
      let dogAge = +prompt('你家狗多大了？')

      // 检查dogAge是否是null或空串
      // if(dogAge !== null && dogAge !== ""){
      //     dogAge = +dogAge;
      // }else{
      //     dogAge = -1;
      // }

      // 创建一个变量用来存储狗的年龄
      let likePersonAge

      //检查用户的输入是否合法
      if (dogAge <= 0 || isNaN(dogAge)) {
        alert('请输入一个正确的年龄！')
      } else {
        // 如果狗的年龄小于两岁
        if (dogAge <= 2) {
          // 使年龄乘以 10.5
          likePersonAge = dogAge * 10.5
        } else {
          // 超过两岁的狗
          likePersonAge = 10.5 * 2 + (dogAge - 2) * 4
        }
        alert(`${dogAge}岁的狗相当于${likePersonAge}岁的人！`)
      }
    </script>
  </head>
  <body></body>
</html>
```

## 32_if 练习

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
        *
        * - 练习4：
          从键盘输入小明的期末成绩:
            当成绩为100时，'奖励一辆BMW'
            当成绩为[80-99]时，'奖励一台iphone'
            当参考书'
            其他时，什么奖励也没有成绩为[60-79]时，'奖励一本
        * */

      // 获取小明的期末成绩
      // let score = +prompt('请输入小明的期末成绩：');
      //
      // // 检查成绩是否合法
      // if (score >= 0 && score <= 100) {
      //     // 当成绩为100时，'奖励一辆BMW'
      //     if (score === 100) {
      //         alert('宝马拿去玩~');
      //     } else if (score >= 80) {
      //         //当成绩为[80-99]时，'奖励一台iphone'
      //         alert('苹果拿去玩~');
      //     } else if (score >= 60) {
      //         //当成绩为[60-79]时，'奖励一本参考书'
      //         alert('参考书拿去读~');
      //     } else {
      //         // 其他时，什么奖励也没有
      //         alert('棍子一根~');
      //     }
      // } else {
      //     // 进入else说明输入不合法
      //     alert('拉出去毙了~');
      // }

      /*



    - 练习5：
          大家都知道，男大当婚，女大当嫁。那么女方家长要嫁女儿，当然要提出一定的条件：
              高：180cm以上; 富:1000万以上; 帅:500以上;
              如果这三个条件同时满足，则:'我一定要嫁给他'
              如果三个条件有为真的情况，则:'嫁吧，比上不足，比下有余。'
              如果三个条件都不满足，则:'不嫁！'
        * */

      // 获取男生的数据
      let height = +prompt('请输入你的身高(CM)：')
      let money = +prompt('请输入你的身价(万元)：')
      let face = +prompt('请输入你的颜值(px)：')

      // alert(`${height} -- ${money} -- ${face}`);

      if (height > 180 && money > 1000 && face > 500) {
        //如果这三个条件同时满足，则:'我一定要嫁给他'
        alert('我一定要嫁给他！')
      } else if (height > 180 || money > 1000 || face > 500) {
        //如果三个条件有为真的情况，则:'嫁吧，比上不足，比下有余。'
        alert('嫁吧，比上不足，比下有余。')
      } else {
        //如果三个条件都不满足，则:'不嫁！'
        alert('不嫁！')
      }
    </script>
  </head>
  <body></body>
</html>
```

## 33_switch 语句

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      // 根据数字显示中文
      // 1 --> 壹   2 --> 贰  3 --> 叁

      // let num = 3;
      //
      // if(num === 1){
      //     alert('壹');
      // }else if(num === 2){
      //     alert('贰');
      // }else if(num === 3){
      //     alert('叁');
      // }

      /*
       *   switch 语句
       *       语法：
       *           switch(条件表达式){
       *               case 表达式:
       *                   语句..
       *                   break;
       *               case 表达式:
       *                   语句..
       *                   break;
       *               case 表达式:
       *                   语句..
       *                   break;
       *               default:
       *                   语句..
       *                   break;
       *           }
       *
       *       执行流程：
       *           switch-case语句在执行时，
       *               会自上向下依次将switch后的条件表达式和ca比较se后的表达式进行全等
       *               如果全等，则自当前case处开始向下执行代码
       *               如果不全等，则继续向下比较，直到找到全等的为止
       *               如果所有的比较都不成立，都是false，则自default处开始执行代码
       *
       *           case后的表达式和switch后的表达式全等时
       *               它是自当前case处开始向下执行代码
       *               也就是即使代码在其他的case下，也会被执行
       *               如果不希望执行其他case后的代码，可以在case后使用break
       *
       *       switch-case 和 if-else的功能基本上是一致的，
       *           if能做的事，switch也行，反之依然，但是使用过程中还是以if为主
       *           当全等的条件比较多时，适合用switch
       *
       * */

      let num = 'a'
      switch (num) {
        default:
          alert('输错了！')
          break
        case 1:
          alert('壹')
          break
        case 2:
          alert('贰')
          break
        case 3:
          alert('叁')
          break
      }

      // switch (num) {
      //     case 1:
      //         alert('壹');
      //         break;
      //     case 2:
      //         alert('贰');
      //         break;
      //     case 3:
      //         alert('叁');
      //         break;
      //     case 'a':
      //     case 'b':
      //     case 'c':
      //     case 'd':
      //         alert('输错了！');
      //         break;
      // }
    </script>
  </head>
  <body></body>
</html>
```

## 34\_循环语句

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   循环语句
       *       - 循环语句可以让指定的代码反复执行多次
       *       - 循环有三种
       *             while语句
       *             do-while语句
       *             for语句
       *
       *   while语句
       *       while(条件表达式){
       *           语句...
       *       }
       *
       *   执行流程
       *       while语句在执行时，会先对条件表达式进行求值判断
       *           如果结果为false，则语句直接结束
       *           如果结果为true，则执行while后的代码（循环体）
       *           执行完毕，继续对条件表达式进行求值判断，以此类推
       *
       * */

      // 条件表达式恒为true的循环，叫做死循环，会一直执行下去（慎用）
      // while(true){
      //     alert('hello');
      // }

      // 循环的三个要件

      // 初始化表达式，创建一个变量来控制循环的执行
      // let i = 0;
      //
      // // 条件表达式，设置循环的执行条件
      // while(i < 10){
      //     console.log(i);
      //     // 更新表达式，修改初始化变量
      //     i++;
      // }

      // let i = 1;
      //
      // while (i <= 8848){
      //     document.write(`${i}.今天天气真不错<br>`);
      //     i++;
      // }

      let i = 0

      while (true) {
        console.log(i)
        i++

        if (i === 5) {
          break // break也可以用来结束循环语句
        }
      }
    </script>
  </head>
  <body></body>
</html>
```

## 35_while 练习

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   假设存款的年利率为5%，问1000存多少年能变成5000？
       *
       *   1000 * 0.05
       *
       * */

      // console.log(1000 * 1.05);

      // 创建一个变量表示钱
      let money = 1000

      // 存一年
      // money *= 1.05;
      // money *= 1.05;
      // money *= 1.05;

      // 定义一个计数器
      let count = 0

      // 创建一个循环，来模拟存钱的情况
      while (money < 5000) {
        money *= 1.05
        count++
      }

      console.log(`一共存了${count}年！`)
    </script>
  </head>
  <body></body>
</html>
```

# day04

## 36 do-while 循环

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
            - do-while循环
                do{
                    语句..
                }while (条件表达式)

            - 执行流程：
                do-while循环在执行时，会先执行循环体，
                    执行完毕对条件表达式进行求值判断
                    如果为false，则语句结束
                    如果为true，则继续执行循环体
                    以此类推

                do-while是先执行后判断，while是先判断后执行
                    do-while可以确保循环至少一次，其他的时候和while没有区别

        */

      let i = 5
      // while (i < 5){
      //     console.log(i);
      //     i++;
      // }

      do {
        console.log(i)
        i++
      } while (i < 5)
    </script>
  </head>
  <body></body>
</html>
```

## 37 \_for 循环

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      // let i = 0;
      // while (i < 5){
      //     console.log(i);
      //     i++;
      // }

      /*
       *   for循环
       *       - 语法：
       *           for(①初始化表达式; ②条件表达式; ④更新表达式){
       *               ③语句...
       *           }
       *
       *       - 执行流程：
       *           for循环在执行时：
       *           ① 先执行初始化表达式，初始化一个变量（只会执行一次）
       *           ② 执行条件表达式，判断循环是否执行
       *               如果为false，则循环结束
       *           ③ 如果为true，则执行循环体
       *           ④ 执行更新表达式对变量进行更新
       *           ⑤ 重复②
       * */

      // for(let i=0; i<5; i++){
      //     console.log(i);
      // }

      /*
        for循环中的表达式都可以省略不写
         */
      // for(;;){
      //     alert('hello');
      // }

      // while (true){
      //
      // }

      /*
        *
        *  练习6：
                求100以内所有的奇数之和
            练习7：
                求100以内所有7的倍数之和，以及个数
        * */
    </script>
  </head>
  <body></body>
</html>
```

## 38_for 练习

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
        * 练习6：
               求100以内所有的奇数之和
        * */

      // // 创建一个变量存储结果
      // let sum = 0;
      // // 获取到100以内所有的数
      // for(let i=0; i<=100; i++){
      //     // 判断i是否是奇数
      //     if(i % 2 !== 0){
      //         sum += i;
      //     }
      // }
      // console.log(sum);

      // let sum = 0;
      // for(let i=1; i<100; i+=2){
      //     sum += i;
      // }
      // console.log(sum);

      /*
      *
      *
          练习7：
              求100以内所有7的倍数之和，以及个数
      * */

      // 记录和
      let sum = 0
      // 创建一个计数器
      let count = 0

      //获取所有的7的倍数
      for (let i = 7; i < 100; i += 7) {
        sum += i
        count++
      }

      console.log(`7的倍数有${count}个，和为${sum}`)
      console.log(i)
    </script>
  </head>
  <body></body>
</html>
```

## 39_for 练习

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
           练习8：
               水仙花数是指一个 n 位数（n≥3 ），它的每个位上的数字的 n 次幂之和等于它本身（例如：1**3 + 5**3 + 3**3 = 153）。
               求 1000 以内所有的水仙花数！
       */

      // 获取所有的三位数
      for (let i = 100; i < 1000; i++) {
        // 获取i的百位数字
        let bai = parseInt(i / 100)

        // 获取i的十位数
        let shi = parseInt((i - bai * 100) / 10)

        // 获取i的个位数字
        let ge = i % 10
        // console.log(`百位数:${bai}，十位数:${shi}，个位数:${ge} ---> ${i}`);

        // 判断 i 是不是水仙花数
        // 如果i的百位立方 + 十位立方 + 个位的立方 = i，则说明i是水仙花数

        if (bai ** 3 + shi ** 3 + ge ** 3 === i) {
          // 进入判断，说明i是水仙花数，打印i
          console.log(i)
        }
      }

      /*
            练习9：
            获取用户输入的任意数，判断其是否是质数。
          质数也叫素数，一个数如果只能被1和它本身整除，那么这个数就是质数。1不是质数也不是合数。

         */

      //let num = +prompt('请输入一个整数:');
      // 检查num是否是质数
    </script>
  </head>
  <body></body>
</html>
```

## 40\_质数练习.html

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      // 创建一个数
      let num = 5

      // 检查num是否质数
      // 如果 5 只能被 1 和 5 整除，那么5就是质数
      // 如果 5 只有 1 和 5 两个因数，那么5就是质数
      // 如果 num 只能被 1 和 num整除，那么num就是质数
      //     检查num是不是质数，只需检查 num 有没有 1和num以外的因数
      //       如果有，num不是质数
      //       如果没有，num是质数

      // 获取到所有的可能整除num的数
      // 获取到 1-num之间的所有数，检查这些数能否整除num
      //   如果都不能整除num，则num是质数
      //   如果有任意一个能整除num，则num不是质数

      num = +prompt('请输入一个正整数：')
      // 创建一个变量，记录检查的状态，默认认为num是质数
      let flag = true
      // 获取到 1-num之间的所有数，检查这些数能否整除num
      for (let i = 2; i < num; i++) {
        // i 现在就是所有的可能整除num的数
        // 检查 num 能否 被i整除
        if (num % i === 0) {
          // 如果num不能被i整除，则说明num是质数 （错的）
          // 如果num能被i整除，则说明num一定不是质数 (对的)
          // 进入判断，说明 num 一定不是质数， 修改flag的值位false
          flag = false
        }
      }

      // 输出结果
      if (flag) {
        // num是质数
        alert(`${num} 是质数！`)
      } else {
        alert(`${num} 不是质数！`)
      }

      // for(let i=2; i<num; i++){
      //     if(num % i === 0){
      //         alert(`${num}不是质数！`);
      //     }else{
      //         alert(`${num}是质数！`);
      //     }
      // }
    </script>
  </head>
  <body></body>
</html>
```

## 41\_循环嵌套.html

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>嵌套循环</title>
    <script>
      /*

            在网页中打印一个图形：
                *****
                *****
                *****
                *****
                *****


                *
                **
                ***
                ****
                *****
        */

      /*
       *   当循环发生嵌套时，外层循环每执行一次，内层循环就执行一圈
       * */

      // 创建一个循环来控制图形的高度
      // for(let i=0; i<5; i++){
      //     // 创建一个内层循环来控制图形的宽度
      //     for(let j=0; j<5; j++){
      //         document.write('*&nbsp;&nbsp;');
      //     }
      //     document.write('<br>');
      // }

      /*


        *     j<1  i=0
        **    j<2  i=1
        ***   j<3  i=2
        ****  j<4  i=3
        ***** j<5  i=4


        *****  j<5  i=0
        ****   j<4  i=1
        ***    j<3  i=2
        **     j<2  i=3
        *      j<1  i=4


        */

      for (let i = 0; i < 5; i++) {
        // 创建一个内层循环来控制图形的宽度
        for (let j = 0; j < i + 1; j++) {
          document.write('*&nbsp;&nbsp;')
        }
        document.write('<br>')
      }

      // for(let i=0; i<5; i++){
      //     // 创建一个内层循环来控制图形的宽度
      //     for(let j=0; j<5-i; j++){
      //         document.write('*&nbsp;&nbsp;');
      //     }
      //     document.write('<br>');
      // }

      /*
            练习一：
                在网页中，打印 99乘法表：
                1x1=1
                1x2=2 2x2=4
                1x3=3 2x3=6 3x3=9
                .....
                                    9x9=81


            练习二：
                求100以内所有的质数。


        */
    </script>
  </head>
  <body></body>
</html>
```

## 42_99 乘法表.html

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>99乘法表</title>
    <style>
      span {
        display: inline-block;
        width: 100px;
      }
    </style>
    <script>
      /*
        练习一：
                在网页中，打印 99乘法表：
                1x1=1
                1x2=2 2x2=4
                1x3=3 2x3=6 3x3=9
                .....
                                    9x9=81
        * */

      //    创建一个外层循环，来控制图形的高度
      for (let i = 1; i <= 9; i++) {
        // 创建一个内层循环，来控制图形的宽度
        for (let j = 1; j < i + 1; j++) {
          document.write(`<span>${j} × ${i} = ${j * i}</span>`)
        }
        // 输出一个换行
        document.write('<br>')
      }
    </script>
  </head>
  <body></body>
</html>
```

## 43 质数练习

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   求100以内所有的质数
       * */

      // 获取100以内所有的数
      for (let i = 2; i < 100; i++) {
        // 检查i是否是质数，是质数则将其打印
        // 默认认为i是质数，创建一个变量，记录i的状态
        let flag = true

        // 获取所有可能整除i的数（除了1和i本身）
        for (let j = 2; j < i; j++) {
          // 检查i能否被j整除
          if (i % j === 0) {
            // 进入判断，说明i一定不是质数，修改flag为false
            flag = false
          }
        }

        //判断
        if (flag) {
          console.log(i)
        }
      }
    </script>
  </head>
  <body></body>
</html>
```

## 44_break 和 continue

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   break
       *       - break用来结束switch和循环语句
       *       - break默认只会影响到离他最近的循环
       *
       *   continue
       *       - continue用来跳过当次循环
       * */

      // for(let i=0; i<5; i++){
      //     console.log('外层循环:',i);
      //
      //     for(let j=0; j<5; j++){
      //         if(j === 2){
      //             break;
      //         }
      //         console.log('---->内层循环:',j);
      //     }
      // }

      // for(let i=0; i<5; i++){
      //     if(i === 2){
      //         continue;
      //     }
      //     console.log(i);
      // }

      for (let i = 0; i < 5; i++) {
        console.log('外层循环:', i)

        for (let j = 0; j < 5; j++) {
          if (j === 2) {
            continue
          }
          console.log('---->内层循环:', j)
        }
      }
    </script>
  </head>
  <body></body>
</html>
```

## 45\_性能优化

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   优化前：
       *       10000 ---> 360ms
       *       100000 ---> 34887ms
       *
       *   第一次优化：
       *       10000 ---> 45ms
       *       100000 ---> 3014ms
       *       1000000 ---> 259011ms
       *
       *   第二次优化：
       *       10000  ---> 12ms
       *       100000  ---> 119ms
       *       1000000  ---> 2568ms
       *
       *
       *   36的因数
       *       1  36
       *       2  18
       *       3  12
       *       4  9
       *       6  6
       *
       * */
      // 开启一个计时器
      console.time()

      // console.log(2);

      for (let i = 3; i < 1000000; i += 2) {
        let flag = true
        for (let j = 2; j <= i ** 0.5; j++) {
          if (i % j === 0) {
            flag = false
            // 进入判断说明i一定不是质数，此时内层循环没有再运行的必要了
            break
          }
        }
        if (flag) {
          // console.log(i);
        }
      }

      // 关闭计时器
      console.timeEnd()
    </script>
  </head>
  <body></body>
</html>
```

# day05

## 46\_对象

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>对象</title>
    <script>
      /*
            基本数据类型（不可变类型）
                - Number
                - String
                - Boolean
                - Null
                - Undefined

            对象（Object）
                - 对象就是JS中的一种数据类型
                - 基本数据类型都是一个一个独立的值，
                    值与值之间不存在任何的联系
                    这样就导致我们无法在程序中来表示一些复杂的数据

                - 对象相当于是一个容器（复合数据类型），在对象中可以存储不同类型的数据
                  对象中存储的数据被称为 属性，向对象中添加数据称为添加属性
        */

      // 创建一个空的对象
      let obj = new Object()

      /*
       *   向对象中添加属性：
       *       对象.属性名 = 属性值;
       * */
      obj.name = '孙悟空'
      obj.age = 18
      obj.gender = '男'

      /*
       *   读取对象中的属性：
       *       对象.属性名
       *       - 当我们访问一个对象中没有的属性时，不会报错而是返回undefined
       *
       *   删除属性：
       *       delete 对象.属性名
       * */

      delete obj.gender

      console.log(obj.gender)
    </script>
  </head>
  <body></body>
</html>
```

## 47\_属性

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>属性</title>
    <script>
      /*
            属性
                属性名：
                    对象的属性是任意值，不必须遵守标识符的规范
                       但是如果你起的名字太特殊，必须采取另外的方式进行命名：
                            对象['属性名'] = 属性值
                       虽然如此，属性名尽量要遵循标识符的规范

                 读取属性的第二种方式：
                        对象['属性名']
                        - 这种方式读取属性更加灵活


        */
      let obj = Object()

      obj.name = '孙悟空'
      obj.age = 18
      obj.gender = '男'

      let a = 'gender'

      // console.log(obj[a]);

      /*
            属性值：
                对象的属性值可以是任意的数据类型
        * */
      obj.test = Object()
      obj.test.name = '猪八戒'

      console.log(obj)
    </script>
  </head>
  <body></body>
</html>
```

## 48\_可变类型

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      let a = 10
      let b = a
      a++
      /*
       *   当一个变量的值被修改时，只会影响它自己，对其他变量不会产生任何影响
       * */

      // console.log('a =', a);
      // console.log('b =', b);

      /*
       *   当我们对对象进行修改时（改对象），如果有其他的变量同时指向该对象
       *       则也会被影响到
       * */
      let obj = Object()
      obj.name = 'swk'
      let obj2 = obj
      obj.name = 'zbj'

      // console.log(obj);
      // console.log(obj2);

      /*
       *   改变量对其他变量不会有影响
       *       变量 = xxx
       *       变量 += xxx
       *       变量++
       *
       *   改对象会影响到其他指向该对象的变量
       *       变量.属性 = xxx
       *
       * */

      let obj3 = Object()
      obj3.name = '白骨精'
      let obj4 = obj3

      // obj3 = null;
      // console.log(obj3);
      // console.log(obj4);

      let obj5 = Object()
      obj5.name = '蜘蛛精'
      let obj6 = Object()
      obj6.name = '蜘蛛精'

      console.log(obj5)
      console.log(obj6)
    </script>
  </head>
  <body></body>
</html>
```

## 49 对象

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      let obj = Object()
      let obj2 = Object()

      /*
       *   比较两个对象时，无论是相等还是全等比较都是对象的内存地址
       * */
      obj.name = '孙悟空'
      obj2.name = '孙悟空'

      obj2 = obj

      // console.log(obj === obj2);

      // 声明常量是禁止修改变量，不会影响我们修改对象
      const obj3 = Object()
      obj3.name = '猪八戒'

      obj3.name = '孙悟空'

      console.log(obj3)
    </script>
  </head>
  <body></body>
</html>
```

## 50\_属性的枚举

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      let obj = Object()

      /*
            检查一个对象中是否含有某个属性
        in 运算符 用来检查对象中是否含有某个属性
          有返回true， 没有返回false
          语法：
            '属性名' in 对象

          */
      // console.log('name' in obj);

      /*
       *   for-in 用来对对象中的属性进行枚举，就是将对象中属性全都取出来
       *   语法：
       *   for(let 变量 in 对象){
       *       语句...
       *   }
       *
       *   for-in会执行多次，对象中有几个属性就会执行几次，
       *       每次执行都会将一个属性名赋值我们定义的变量
       * */
      obj.name = '孙悟空'
      obj.age = 18
      obj.gender = '男'
      obj.address = '花果山'

      for (let n in obj) {
        // console.log('n =',n);

        console.log(n, '=', obj[n])
      }
    </script>
  </head>
  <body></body>
</html>
```

## 51\_对象的补充

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
            对象字面量
                - 以字面量的形式来创建对象
                - 可以之间使用{}来创建一个对象
                - 使用typeof检查一个对象时 会返回 'object'

                - 字面量可以在创建对象时直接向对象中添加属性
                - 语法：
                    {
                        属性名:属性值,
                        属性名:属性值,
                        属性名:属性值
                    }
        * */

      let obj = {
        name: '孙悟空',
        age: 18,
        gender: '男',
      }
      // let obj2 = Object();
      //
      console.log('obj =', obj)
      // console.log('obj2 =', obj2, typeof obj2);

      let obj2 = {
        name: '孙悟空',
        brother: {
          name: '猪八戒',
        },
      }
    </script>
  </head>
  <body></body>
</html>
```

## 52\_垃圾回收

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   垃圾回收（垃圾收集 GC）
       *       就像在生活中会产生垃圾一样，在程序运行一段时间后也会产生垃圾
       *           生活中的垃圾会影响到生活品质，程序中的垃圾会影响程序的运行速度
       *
       *       如果一个对象，没有任何的变量对其进行引用，那么这个对象就是垃圾对象
       *           垃圾对象大量存在会占用大量内存空间导致程序速度变慢，
       *           必须要及时将这些垃圾进行清理
       *
       *       但是这些垃圾对象我们不需要处理，因为在JS中拥有自动的垃圾收集机制，
       *           它会将垃圾对象从内存中清除，我们要做的就是将不再使用的变量设置为null
       * */

      let obj = {}
      let obj2 = {}
      let obj3 = {}
      // obj.test = obj3;
      obj3 = null
    </script>
  </head>
  <body></body>
</html>
```

## 53\_函数

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   函数（function）
       *       - 函数也是一个对象和其他的对象功能一样
       *       - 不同的是在函数中可以直接存储JS代码，
       *           并且可以在我们需要的时候对这些代码进行反复的调用
       *
       * */

      // {
      //     alert('你好！');
      //     alert('Hello!');
      //     alert('扣你吉瓦！');
      //     alert('啊你哈萨有！');
      // }

      /*
       * 创建一个函数
       * */
      function fn() {
        alert('你好！')
        alert('Hello!')
        alert('扣你吉瓦！')
        alert('啊你哈萨有！')
        alert('萨瓦迪卡')
      }

      /*
       *   调用函数：
       *       函数对象 + ()
       * */
      fn()
      fn()
      fn()
    </script>
  </head>
  <body></body>
</html>
```

## 54\_函数

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
            函数声明：
                function 函数名([形参1,形参2,....形参N]){
                    语句...
                }
        */

      function fn() {
        console.log('hello')
      }

      // 打印函数对象
      // console.log(fn);
      // 调用函数 函数对象() 调用函数就是执行函数中存储的代码
      // fn();

      /*
            函数表达式：
                let fn2 = function([形参1,形参2,....形参N]){
                    语句...
                };
        */

      let fn2 = function () {
        console.log('我是fn2')
      }

      // fn2();

      /*
            定义一个函数可以用来求任意两个数的和

            形参（形式参数）：
                - 在定义函数时，可以在函数的()中指定数量不等的形参
                - 定义形参就相当于在函数中声明了两个变量
                    但是没有赋值
            实参（实际参数）：
                - 在调用函数时，可以在函数的()中传递数量不等的实参
                    实参将会赋值给对应的形参
                - JS中不会检查实参的类型和数量
                    - 可以传递任意类型的实参
                    - 也可以传递任意数量的实参
                        如果实参和形参的数量相同，则对应的实参赋值给对应形参
                        如果实参少于形参的数量，则没有实参的形参默认为undefined
                        如果实参多余形参，则多余的实参不会使用


        */
      // function sum(a, b) {
      //     // console.log('a =', a, 'b =',b);
      //     if(typeof a === 'number' && typeof b === 'number'){
      //         console.log(a + b);
      //     }else{
      //         console.log('类型错误！不给算！');
      //     }
      // }

      function sum(a, b) {
        console.log('a =', a, 'b =', b)
      }

      sum(33, 44, 55, 66)
    </script>
  </head>
  <body></body>
</html>
```

## 55\_函数

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   返回值：
       *       - 返回值就是函数的执行结果
       *       - 通过return来设置函数的返回值
       *           语法：return 值;
       *       - 任何值都可以作为函数的返回值
       *       - 如果不设置return 或 return 不跟任何值
       *           则相当于 return undefined
       *       - return 后的所有代码都不会执行
       *           return执行后 函数立即结束
       * */
      function sum(a, b) {
        return a + b
      }

      // 调用函数时，返回值就是函数的执行结果，可以定义一个变量来接收结果
      let s = sum(123, 456)

      // console.log(s);

      function fn() {
        // return {name:'孙悟空'};
        // return function () {
        //     console.log('我是内部函数！');
        // };

        return

        console.log('我是return后的代码！！')
      }

      let result = fn()

      // console.log(result);
      // result();

      function fn2() {
        console.log('函数开始执行了~~~')

        for (let i = 0; i < 5; i++) {
          if (i === 2) {
            // break;
            // continue;
            return
          }
          console.log(i)
        }

        console.log('函数执行结束了~~~')
      }

      fn2()
    </script>
  </head>
  <body></body>
</html>
```

## 56\_函数的参数和返回值

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   参数可以是任意类型的值
       * */
      // fn(1, true);

      // fn('hello', null);

      // fn('abc', {});

      // fn(true, function () {console.log('hello');});

      function fn(a, b) {
        a++ // 是a自增
        console.log('a =', a)
        // b = {name:'猪八戒'}; // 改变量
        b.name = '猪八戒' // 改对象
        console.log('b =', b)
      }

      let a = 10
      let b = { name: '孙悟空' }

      // fn(a, b);
      // console.log("a =", a);
      // console.log("b =", b);

      function fn2() {
        let a = 10
        let b = 20
        // return {a:a, b:b};
        // return {a, b};

        return function () {
          console.log('hello')
        }
      }

      let result = fn2()

      // console.log(result);

      // IIFE(Immediately Invoked Function Expression)
      // 立即执行函数，会在函数创建后立刻调用，并且只会调用一次
      /*
         (function(){})()

         (function(){}())
        */

      // JS禁止一个以function开头的函数没有名字
      ;(function () {
        console.log('我是一个匿名函数~~')
      })()
    </script>
  </head>
  <body></body>
</html>
```

## 57\_方法

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>方法</title>
    <script>
      // (function () {
      //     console.log('匿名函数1');
      // }());
      //
      // (function () {
      //     console.log('匿名函数2');
      // }());

      /*
            使用typeof检查一个函数时，会返回function
        *   任何值都可以成为对象的属性，函数也不例外
            如果一个对象的属性是函数，
                则我们称这个函数是这个对象的方法（method）
                调用函数就称为调用xx对象的xx方法

                函数和方法目前来讲只是称呼的不同，没有本质区别
        * */

      let obj = {
        test: function () {
          alert('我是obj中函数')
        },
        tt: function () {
          alert('嘻嘻嘻')
        },
      }

      obj = {
        test() {
          alert('哈哈哈')
        },
        tt() {
          alert('嘻嘻嘻')
        },
      }

      // console.log(typeof obj.test);
      obj.tt()
    </script>
  </head>
  <body></body>
</html>
```

## 58\_作用域

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>作用域</title>
    <script>
      /*
            作用域（scope）
                - 作用域指的就是变量的作用范围
                - 作用域分为两大类：
                    全局作用域
                    局部作用域
                        - 块作用域
                        - 函数作用域

                - 全局作用域（global）
                    - 全局作用域在页面加载时创建，在页面关闭时销毁
                    - 所有的直接写在script标签中的内容，都位于全局作用域中
                    - 全局作用域中定义的变量是全局变量，定义的函数是全局函数
                        全局变量和全局函数可以在任意位置被访问到
                    - 全局作用域中存在有一个全局对象 window，window对象代表浏览器窗口
                        在全局作用域中，所有的使用var声明的变量，都会作为window对象的属性保存
                          使用function声明的函数都会作为window对象方法保存
                          函数实际上就是window对象的方法！

                     - let声明的变量不会存储在window对象中


        */

      var a = 10
      var b = 20

      function fn() {
        console.log(a)
        console.log(b)
      }

      // window.fn();

      // window.a = 44;
      // alert(a);
      // alert(window.a);

      // window.alert('hello');

      // 直接为一个没有声明的变量赋值，实际就相当于直接向window对象中添加属性
      // window.c = 30;
      // c = 30;
    </script>
  </head>
  <body></body>
</html>
```

## 59\_变量提升

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *
       * 在JS中，使用var声明的变量，
       *   会在所有的代码执行前被创建，但是不会赋值
       *   所以我们可以在变量声明前就对其进行访问
       *   这个特点称为变量的提升！
       *
       * 使用function开头的函数，会在所有代码执行前被创建
       *   所以我们可以在函数声明前就对其进行调用
       *   这个特点称为函数的提升！
       * */

      console.log(a)
      var a = 10
      console.log(a) //undefined
      console.log(fn) /**
         function fn() {
            console.log('函数1');
        }
         */

      // 函数声明
      function fn() {
        console.log('函数1')
      }
      console.log(fn) /**
         function fn() {
            console.log('函数1');
        }
         */
      console.log(fn2) //undefined

      // 函数表达式
      var fn2 = function () {
        console.log('函数2')
      }

      console.log(fn2)
      fn2()
    </script>
  </head>
  <body></body>
</html>
```

# day06

## 60_debug

注意在前端页面上 debug 的快捷键：

F9 是跳入下一步。

注意：F10 是跳入函数内部，以及 shift+F10 是则是跳出函数内部。

## 61\_函数作用域

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   函数作用域：
       *       - 函数作用域在函数调用时创建，调用结束时销毁
       *       - 函数每次调用都会产生一个新的函数作用域
       *           每个作用域间是相互独立的
       *       - 在函数作用域中声明的变量是局部变量
       *           局部变量只能在函数内部访问，外部无法访问
       *           注意：在函数中声明变量时如果不使用var或let
       *               则变量会变成全局变量（一定要注意）
       *       - 在函数作用域中可以访问全局作用域的变量
       *           但是在全局作用域中无法访问函数作用域的变量
       *       - 变量和函数的提升，在函数作用域中同样适用
       * */

      function fn() {
        let a = 10
        var b = 20

        function test() {
          let c = 30
          console.log(a, b)
        }

        // console.log(c);
        test()
      }

      fn()
    </script>
  </head>
  <body></body>
</html>
```

## 63\_作用域

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *
       * 作用域链：
       * 当我们访问一个变量时，JS会先在当前作用域中寻找
       *   如果有则直接使用
       *   如果没有，则去当前作用域的上一层作用域寻找
       *   找到了则直接使用，没找到继续去上一层寻找，以此类推
       *   直到找到全局作用域，如果没有找到则报错 xxx is not defined
       *
       *
       * JS中的作用域叫做 词法作用域，简单说，函数作用域由它定义的位置来决定的，
       *   和调用位置无关。
       *
       * 函数的定义在哪，它的上一层就是哪
       *
       *
       *
       * */

      // let a = 10;

      function fn() {
        // let a = 20;
        function test() {
          console.log('a =', a)
        }
        test()
      }

      // fn();

      let b = 22

      function fn2() {
        console.log('b =', b)
      }

      function fn3() {
        let b = 33
        fn2()
      }

      // fn3();

      function fn4() {
        let b = 44

        return function () {
          console.log('b =', b)
        }
      }
      let fn5 = fn4()
      b = 22
      fn5()
    </script>
  </head>
  <body></body>
</html>
```

## 64\_练习

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*        let a = 10;
        function fn(){
             a = 20;
            console.log(a);
        }
        fn();
        console.log(a); */ //结果是  20  20

      /*      let a = 10;
        function fn(){
            let a = 20;
            console.log(a);
        }
        fn();
        console.log(a);*/ //结果是 20 10

      /*        let a = 10;
        function fn(){
            a = 20;
            var a = 30;
            console.log(a);
        }
        fn();
        console.log(a);*/ //结果是 30  10

      /*        let a = 10;
        function fn(a){
            a = 20;
            console.log(a);
        }
        fn();
        console.log(a);//结果是20 10*/

      /*        let a = 10;
        function fn(a){
            console.log(a);
            a = 20;
            console.log(a);
        }
        fn(a);
        console.log(a);*/ //10 20 10

      /*let a=10;
fn()
function fn(a) {
    a=100;
    console.log(a)
}*/
      let a = 10
      function fn(b) {
        console.log(a)
        var a = 12
        console.log(a)
        a = 100
        console.log(a)
      }
      fn(a)
      /*当形参与参数名同名时，需要严格注意变量提升
       *
       * * */
      console.log(a)

      /*函数提升优先级高于变量提升*/

      function method1() {
        console.log('方法1')
      }
      console.log(method1)
      var method1 = 'kaka'
      console.log(method1)
    </script>
  </head>
  <body></body>
</html>
```

## 65\_作用域

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      let a = 10

      function fn2() {
        let a = 20
        fn()

        function fn() {
          console.log(a)
        }
      }

      fn2()
    </script>
  </head>
  <body></body>
</html>
```

## 66_this

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      // 设置一个全局变量name
      var name = '全局的name属性'

      // console.log(name);
      // console.log(window.name);

      // 定义一个对象
      var obj = {
        name: '孙悟空',
        sayHello: fn,
      }

      var obj2 = {
        name: '猪八戒',
        sayHello: fn,
      }

      // console.log(obj.sayHello === fn);
      // obj.sayHello();
      // obj2.sayHello();
      // fn();
      /*
       *   希望：
       *       obj.sayHello() ---> 孙悟空 --> obj.name
       *       obj2.sayHello() ---> 猪八戒 --> obj2.name
       *       window.fn() ---> 全局的name属性 --> window.name
       *       谁调用的方法就打印谁的name属性
       * */
      // 定义一个函数
      function fn() {
        console.log(this.name)
        // console.log(obj2.name);
        // console.log(window.name);

        /*
                在调用函数时，浏览器每次都会向函数中传递一个隐含的参数，
                    这个参数的名字叫做this, this指向的是一个对象！

                this到底是谁呢？
                    1. 当我们以函数的形式调用一个函数时，this是window
                    2. 当我们以方法的形式调用一个函数是，this是调用方法的对象

            * */

        // console.log(this);
      }

      // obj.sayHello(); //obj
      // fn(); // window
      // window.fn(); // window
      // obj2.sayHello(); // obj2

      name = '沙和尚'

      let obj3 = {
        name: '孙悟空',
        sayHello: function () {
          alert(this.name)
        },
      }

      obj3.sayHello()
    </script>
  </head>
  <body></body>
</html>
```

## 67\_对象

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      // 创建一个函数，专门用来创建人类的对象
      /*
       *   工厂方法
       *       - 使用工厂方法来创建对象
       * */
      function createPerson(name, age, gender, address) {
        // 创建一个对象
        // let obj = {
        //     name,
        //     age,
        //     gender,
        //     address,
        //     sayHello(){
        //         alert(`大家好，我是${this.name}`);
        //     }
        // };

        let obj = {}

        // // 向对象中添加属性
        obj.name = name
        obj.age = age
        obj.gender = gender
        obj.address = address
        obj.sayHello = function () {
          alert(`大家好，我是${this.name}`)
        }
        //将对象作为返回值返回
        return obj
      }

      let per = createPerson('孙悟空', 18, '男', '花果山')
      let per2 = createPerson('白骨精', 16, '女', '盘丝洞')
      let per3 = createPerson('蜘蛛精', 14, '女', '北七家')

      console.log(per)
      console.log(per2)
      console.log(per3)
    </script>
  </head>
  <body></body>
</html>
```

## 68\_对象

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      function createPerson(name, age) {
        let obj = {}
        obj.name = name
        obj.age = age
        obj.sayHello = function () {
          alert('大家好，我是' + this.name)
        }
        return obj
      }

      function createDog(name, age) {
        let obj = {}
        obj.name = name
        obj.age = age
        obj.sayHello = function () {
          alert('旺旺旺~')
        }
        return obj
      }

      // let per = createPerson('孙悟空', 18);
      // let dog = createDog('旺财', 3);

      // console.log(per);
      // console.log(dog);

      /*
       *   可以通过 构造函数 来创建对象
       *       - 构造函数就是专门用来创建对象的函数
       *       - 构造函数的定义方式和普通函数没有区别
       *           唯一的不同点在于构造函数的名字首字母要大写
       *       - 构造函数和普通函数的区别在于调用方式
       *           一个函数如果直接调用，那么它就是一个普通函数
       *           如果使用new关键字调用，他就是一个构造函数
       *       - 一个构造函数也称为是一个类，通过该构造函数所创建的对象
       *           称为该类实例，通过同一个类创建的对象，称为同一类对象
       *
       *   构造函数的执行流程：
       *       1.创建一个新的对象
       *       2.将这个新的对象设置为函数中的this
       *       3.执行函数中的代码
       *       4.将新建的对象返回
       * */
      function Person(name, age) {
        this.name = name
        this.age = age
      }

      function Dog(name, age) {
        this.name = name
        this.age = age
      }

      let per = new Person('孙悟空', 18)
      let per2 = new Person('猪八戒', 28)
      let dog = new Dog('啸天', 10)

      /*
       *   instanceof
       *       - 用来检查一个对象是否是一个类的实例
       *       - 语法：
       *           对象 instanceof 类（构造函数）
       * */
      console.log(per instanceof Person)
      console.log(dog instanceof Person)
    </script>
  </head>
  <body></body>
</html>
```

# day07

## 69\_构造函数

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      // 定义一个表示人的类
      function Person(name, age) {
        this.name = name
        this.age = age

        /*
         * 现在我们的方法直接定义在了构造函数中，
         *   也就是构造函数，每执行一次，就会创建一个新的函数对象
         *   这样也就意味着，每一个对象都有不同的sayHello()方法
         *   但是，这些sayHello()的功能却是一样的。
         *   而创建许多会占用大量的内存空间，实际完全可以所有的对象都公用一个sayHello()
         * */

        // 向类中添加一个方法
        // this.sayHello = sayHello;
      }

      // 将sayHello()定义为一个全局函数
      // 污染全局的命名空间（namespace）
      // function sayHello() {
      //     alert(`大家好，I'm ${this.name}！`);
      // }

      // 将sayHello，添加到原型中
      Person.prototype.sayHello = function () {
        alert(`大家好，I'm ${this.name}！`)
      }

      // 创建一个人类的实例
      let per = new Person('孙悟空', 18)
      let per2 = new Person('猪八戒', 28)
      let per3 = new Person('沙和尚', 38)

      console.log(per.sayHello === per2.sayHello)

      // per.sayHello();
      // per2.sayHello();
      // per3.sayHello();
    </script>
  </head>
  <body></body>
</html>
```

## 70\_原型

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>原型</title>
    <script>
      /*
       *   每个函数对象中都有一个属性叫做prototype，
       *       该属性指向的是一个对象，这个对象原型对象
       *       如果函数作为普通函数调用，则原型对象（prototype）没有任何作用
       *       如果函数作为构造函数调用，那么通过该构造函数所创建的对象中
       *           都会有一个隐含的属性（__proto__）指向函数的原型对象（prototype）
       *
       *       也就是说，该类的所有实例中都会有一个隐含属性指向构造函数的prototype，
       *           原型对象，就相当于一个公共的区域可以被所有的该类实例访问
       *           可以将一些实例共有的属性或方法存储在原型对象中，
       *               这样只需要设置一次即可让所有的对象都访问到该属性
       *
       *       当我们访问一个对象中的属性时，JS会先在对象本身中寻找，
       *           如果找到了则直接使用，
       *           如果没有找到则去对象的原型(__proto__)中寻找
       *           找到了则使用，如果没有找到则去原型的原型中寻找
       *           如果找到了则使用，如果没有找到以此类推..
       *           直到找到Object的原型，如果依然没有，则返回undefined，不会报错
       *           这个搜索的过程称为原型链
       *
       *           Object的prototype是所有对象的原型，它的原型为null
       *
       *
       *       结论：
       *           定义一个类时，如果属性和方法是对象独有的，就直接在构造函数中设置
       *               function 类名(){
       *                   this.xxx = yyy;
       *               }
       *
       *           如果属性和方法是公共的，每一个对象的值都是相同，可以通过原型来添加
       *               类.prototype.属性名 = 值;
       *
       *
       * */

      function MyClass() {}

      // 向原型中添加一个属性
      MyClass.prototype.name = '原型中的name属性'

      let mc = new MyClass()
      let mc2 = new MyClass()
      let mc3 = new MyClass()

      mc.name = '孙悟空'

      // 访问mc中的隐含属性
      // console.log(mc2.__proto__ === MyClass.prototype);
      console.log(mc.name)
      console.log(mc2.name)
      console.log(mc3.name)
    </script>
  </head>
  <body></body>
</html>
```

## 71\_原型

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      function Person(name, age) {
        this.name = name
        this.age = age
      }

      Person.prototype.test = '公共属性'

      let p1 = new Person('孙悟空', 18)

      // console.log(p1.name, p1.age, p1.test);

      // in运算符在检查一个属性时，如果属性存在于对象的原型中，也会返回true
      // console.log('test' in p1);

      // hasOwnProperty() 用来检查一个属性是否存在于对象自身中
      // console.log(p1.hasOwnProperty('test'));
      // console.log(p1.__proto__.hasOwnProperty('test'));

      // console.log(p1.__proto__.__proto__.__proto__);
      // console.log(p1.address);

      // instanceof 就是检查对象的原型链上是否有类存在
      // Object是所有对象的祖先
      console.log(p1 instanceof Object)
    </script>
  </head>
  <body></body>
</html>
```

## 72\_原型

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      function MyClass() {}

      let mc = new MyClass() // '[object Object]'

      // 如果原型中的方法不能满足我们的需求，可以选择创建一个同名的方法将其覆盖
      // 这称为方法的重写
      mc.toString = function () {
        return 'HELLO'
      }

      // console.log(mc.toString());

      // alert(mc);

      /*
       *   实例的隐式原型指向类（构造函数）的显示原型
       * */
      // MyClass.prototype 显式原型

      // mc.__proto__  隐式原型
      // mc.__proto__.__proto__

      // 获取Object的原型
      // console.log(Object.prototype.__proto__);

      /*
       *   需要你记住的：
       *       1.定义类时，独有的属性（方法）在构造函数中通过this添加
       *       2.公共的方法（属性）在构造函数外部通过原型来添加
       *       3.当我们使用一个对象的属性或方法时，
       *           js会先在对象中找，对象中没有去原型中找，
       *           原型中没有，去原型的原型中找，直到找到object的原型，没有返回undefined
       * */

      // let obj = new Object();
      // obj.hasOwnProperty();
      // Object.assign();

      function Person(name, age) {
        this.name = name
        this.age = age
      }

      Person.prototype.toString = function () {
        return 'Person {name:' + this.name + ', age:' + this.age + '}'
      }

      let p1 = new Person('孙悟空', 18)
      let p2 = new Person('猪八戒', 28)

      alert(p1)
      alert(p2)
    </script>
  </head>
  <body></body>
</html>
```

## 73\_数组

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       * 数组
       *   - 使用[]来创建一个数组，和new Array()效果一致
       *   - 可以在创建数组时，同时向数组中添加元素
       * */
      let arr = [] // arr = new Array();
      arr = [10]
      // arr = new Array(33, 44, 55, 66);
      // arr = new Array(10);

      /*
       *
       * 数组中可以存储的数据类型
       *   - 虽然数组里可以存储任意的数据类型，并且长度没有限制
       *       但是我们在使用数组，要尽量确保数组中的数据类型是相同
       *
       * */

      arr = [
        'hello',
        true,
        null,
        { name: 'swk' },
        function () {
          alert('hello')
        },
      ]

      /*
       *   如果一个数组中的元素还是数组，则这个数组被称为二维数组
       * */
      arr = [
        [1, 2, 3],
        [4, 5, 6],
      ]

      // console.log(arr[0][1]);
      // console.log(arr[3].name);
      // arr[4]();
    </script>
  </head>
  <body></body>
</html>
```

## 74\_数组的遍历

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      let arr = ['孙悟空', '猪八戒', '沙和尚', '唐僧', '蜘蛛精']

      /*
       *   遍历，指的就是获取到数组中的所有元素
       * */
      for (let i = 0; i < arr.length; i++) {
        console.log(arr[i])
      }

      /*for(let i=arr.length - 1; i>=0; i--){
            console.log(arr[i]);
        }*/

      /*for(let i in arr){
            console.log(arr[i]);
        }*/

      /*for(let v of arr){
            console.log(v);
        }*/
    </script>
  </head>
  <body></body>
</html>
```

## 75\_数组的四个方法

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      let arr = ['孙悟空', '猪八戒', '沙和尚', '唐僧', '蜘蛛精']

      /*
       *   push()
       *       - 用来向数组的最后添加一个或多个元素
       *           会返回新的长度
       *   pop()
       *       - 从数组的最后删除一个元素并返回被删除的元素
       *   unshift()
       *       - 向数组的前边添加一个或多个元素，并返回新的长度
       *   shift()
       *       - 删除并返回数组的第一个元素
       * */

      arr.push('白骨精')
      let result = arr.push('玉兔精', '蝎子精')
      arr.pop()
      arr.pop()
      arr.pop()
      result = arr.pop()

      result = arr.unshift('二郎神', '哪吒', '姜子牙', '火龙果')
      result = arr.shift()
      result = arr.shift()
      result = arr.shift()
      result = arr.shift()
      console.log(arr)
      console.log(result)
    </script>
  </head>
  <body></body>
</html>
```

## 76\_练习

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      function Person(name, age) {
        this.name = name
        this.age = age
      }

      let p1 = new Person('孙悟空', 18)
      let p2 = new Person('猪八戒', 28)
      let p3 = new Person('红孩儿', 8)
      let p4 = new Person('白骨精', 16)
      let p5 = new Person('林志玲', 48)
      let p6 = new Person('郭德纲', 12)

      let perArr = [p1, p2, p3, p4, p5, p6]

      /*
       *   定义一个函数，将perArr中的所有成年人筛选到一个新的数组并返回
       * */

      function getAdult(arr) {
        let newArr = []

        //遍历数组
        for (let i = 0; i < arr.length; i++) {
          // 检查当前的人的对象是否成年
          if (arr[i].age >= 18) {
            // 进入判断，证明当前人的对象成年了，将其放入到新数组
            newArr.push(arr[i])
          }
        }

        return newArr
      }

      let result = getAdult(perArr)

      console.log(result)
    </script>
  </head>
  <body></body>
</html>
```

## 77\_数组的方法

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      let arr = ['孙悟空', '猪八戒', '沙和尚', '唐僧']

      /*
            slice() (非破坏性的方法)
                - slice用来截取数组
                - 参数：
                     1.截取的起始位置索引 (包含起始位置)
                     2.截取的结束位置索引 (不包含结束位置)
                - 该方法不会影响到原来的数组，而是将结果作为返回值返回
                - 可以省略第二个参数，如果不写第二个参数，则会一直截取到最后
                — 索引可以传负值 -1表示倒数第一个 -2表示倒数第二个，以此类推


            splice()（破坏性的方法）
                - splice可以用来删除，替换，添加数组中的元素
                - 该方法会对原数组产生影响
                - 参数：
                    1.删除元素起始位置索引
                    2.删除的数量
                    3.可以传递多个参数，这些参数将会作为新元素
                            添加到数组中

                - 返回值：
                     被删除的元素

        *
        * */

      let result = arr.slice(1, 3)
      result = arr.slice(1, 2)
      result = arr.slice(1, -1)
      result = arr.slice(0, 2)

      arr = ['孙悟空', '猪八戒', '沙和尚', '唐僧']
      // result = arr.splice(0, 2); // 删除指定的元素
      // result = arr.splice(0, 2, '牛魔王', '铁扇'); // 替换指定元素
      // result = arr.splice(0, 2, '牛魔王', '铁扇', '小红');
      result = arr.splice(2, 0, '牛魔王', '二郎神') // 向指定位置插入新元素
      console.log(arr)
      // console.log(result);
    </script>
  </head>
  <body></body>
</html>
```

## 78\_练习

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      let arr = [1, 2, 1, 3, 4, 2, 3, 5, 6, 7, 5, 8, 9]

      /*
       *   编写代码，去除数组中重复的数字
       * */

      console.log(arr)

      /*
       *   排序的思路：
       *       比较相邻的两个元素，根据结果交换位置
       *       [1,2,3,4,5,7,6,8,9]
       *       [1,2,3,4,5,6,7,8,9]
       * */

      let arr2 = [3, 8, 2, 9, 5, 7, 4, 6, 1]
      /*
       *   编写代码，对arr2进行从小到大排序
       * */
    </script>
  </head>
  <body></body>
</html>
```

# day08

## 79\_复习

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      let arr = ['孙悟空', '猪八戒', '沙和尚']

      // console.log(arr[arr.length - 3]);

      // arr.push();

      let obj = {}

      // console.log(Array.isArray(obj));
      // console.log(arr instanceof Array);

      let arr2 = ['孙悟空', '猪八戒', '沙和尚']

      // 对arr2进行浅复制（拷贝）
      let arr3 = arr2.slice(0)
      // let arr3 = arr2;

      arr3[3] = '唐僧'

      // console.log(arr2);
      // console.log(arr3);

      let arr4 = [{ name: '孙悟空' }, { name: '猪八戒' }]
      let arr5 = arr4.slice(0)

      // arr5[0] = 'hello';
      // arr5[0].name = '沙和尚';

      console.log(arr4[0] === arr5[0])
      // console.log(arr5);
    </script>
  </head>
  <body></body>
</html>
```

## 80\_练习

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      let arr = [1, 2, 1, 3, 4, 2, 2, 3, 5, 4, 6, 5]

      //    思路：分别取出每个数，和其他的数字进行比较
      // 获取数组中每一个数字
      for (let i = 0; i < arr.length; i++) {
        // console.log(arr[i]);
        // arr[i] 和它后边的元素进行比较
        // 获取到arr[i]后边元素
        for (let j = i + 1; j < arr.length; j++) {
          // arr[i] arr[j]
          // console.log('------>',arr[j]);
          // 比较arr[i] 和 arr[j]
          if (arr[i] === arr[j]) {
            // 全等，说明出现了重复的数字，删除后边的数字j
            arr.splice(j, 1)
            // 当删除一个元素后，后边所有的元素索引自动前移
            // 这回导致有元素会错过比较
            // 执行j--，将当前位置在比较一遍
            j--
          }
        }
      }

      // console.log(arr);

      arr = [2, 1, 2, 3, 2, 4, 3, 3, 5, 4, 6, 5, 7]

      let newArr = []

      for (let i = 0; i < arr.length; i++) {
        // if(!(arr[i] in newArr)){
        //     newArr.push(arr[i]);
        // }

        if (newArr.indexOf(arr[i]) === -1) {
          newArr.push(arr[i])
        }
      }

      console.log(newArr)
    </script>
  </head>
  <body></body>
</html>
```

## 81\_排序

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      let arr = [9, 1, 3, 4, 5, 7, 8, 6, 2]
      // arr = [9,8,7,6,5,4,3,2,1];
      // arr = [2,1,3,4,5,6,7,8,9];

      /*
       *   编写代码，对arr进行从小到大的排序
       *       比较相邻的两个数字，然后根据情况交换位置
       *       [9,1,3,4,5,7,8,6,2]
       *       1. [1,3,4,5,7,8,6,2,9]
       *       2. [1,3,4,5,7,6,2,8,9]
       *       2. [1,3,4,5,7,6,2,8,9]
       *
       *   这种排序方式被称为冒泡排序，它是最好理解的排序方式
       *       同时也是性能最差的排序方式
       *
       * */

      console.log('原数组：', arr)

      for (let j = 0; j < arr.length - 1; j++) {
        // 遍历数组，获取到所有的元素
        for (let i = 0; i < arr.length - 1 - j; i++) {
          //当前数 arr[i]   后边数 arr[i+1]
          // console.log(arr[i], arr[i+1]);
          if (arr[i] > arr[i + 1]) {
            // 前边的数字大于后边的数字，需要交换两个元素的位置
            let temp = arr[i]
            arr[i] = arr[i + 1]
            arr[i + 1] = temp
          }
        }
      }

      console.log(arr)
    </script>
  </head>
  <body></body>
</html>
```

## 82_forEach

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>

    <script>
      let arr = ['孙悟空', '沙和尚', '猪八戒', '唐僧']

      // for(let i=0; i<arr.length; i++){
      //     console.log(arr[i]);
      // }

      /*
       *   forEach()
       *      - forEach()专门用来对数组进行遍历
       *       该方法需要一个函数作为参数
       *
       *       - 像这种由我们定义，但是不由我们调用的，
       *           这种函数被称为 回调函数（callback）
       *
       *       - forEach()的回调会被调用多次，
       *           数组有几个元素，函数就调用几次
       *           forEach()通过回调函数，将元素传递出来
       *       - 元素信息将会以参数的形式传递进行回调函数
       *           我们可以通过定义形参来获取元素的信息
       *           forEach()的回调函数共有三个参数：
       *           1. 当前被遍历的元素
       *           2. 当前遍历的元素的索引
       *           3. 当前正在被遍历的数组对象
       *
       * */

      // function fn(){
      // }

      arr.forEach(function (element, index, array) {
        // console.log('element =', element);
        // console.log('index =', index);
        // console.log('array =', array);

        console.log(index, element)
      })
    </script>
  </head>
  <body></body>
</html>
```

## 83\_数组的方法

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      let arr = ['孙悟空', '猪八戒', '沙和尚']
      let arr2 = ['白骨精', '蜘蛛精', '玉兔精']

      /*
       * concat()
       *   - 用来连接两个个或多个数组
       *   - concat()不会影响原数组，而是将元素拼接到一个新数组中返回
       *
       * indexOf()
       *   - 查询元素在数组中的位置
       *   - 参数：
       *       1.要查询的元素
       *       2.查询的起始位置
       *
       *   - 返回值：
       *       返回元素第一次在数组中出现的索引，
       *           如果没有找到元素，则返回-1
       *
       * lastIndexOf()
       *   - 查询元素在数组中的位置
       *   - 参数：
       *       1.要查询的元素
       *       2.查询的起始位置
       *   - 返回值：
       *       返回元素最后一次出现的索引，找不到返回-1
       *
       *  join()
       *   - 用来将数组中的所有元素连接为一个字符串
       *   - 参数：
       *       1.指定一个连接符（字符串）作为参数
       *           如果不指定，则默认使用,
       *
       *   reverse()
       *    - 用来对数组进行反转，这是一个破坏性的方法，会改变原数组
       *
       *   sort()
       *    - 用来对数组进行排序的，也会影响到原数组
       *    - 使用sort()对元素进行排序的时候，比较的是元素的字符编码而不是数字的大小
       *    - 可以在sort()通过回调函数来指定排序规则
       *           如果希望升序排列 （从小到大排列）
       *               function(a, b){
       *                   return a-b;
       *               }
       *
       *           如果希望降序排列（从大到小排）
       *               function(a, b){
       *                   return b-a;
       *               }
       *
       * */
      let result = arr.concat(arr2, ['牛魔王', '二郎神'], '哈哈')

      arr = ['孙悟空', '猪八戒', '孙悟空', '沙和尚']

      result = arr.indexOf('孙悟空')
      result = arr.indexOf('唐僧')
      result = arr.indexOf('孙悟空', 1)
      result = arr.lastIndexOf('孙悟空')

      arr = ['a', 'b', 'c', 'd']

      result = arr.join('@-@')
      result = arr.join('')

      arr.reverse()

      // console.log(arr);
      // console.log(result);

      arr = ['b', 'c', 'e', 'f', 'g', 'a']
      arr = [3, 2, 1, 4, 5, 8, 9, 7, 6, 10]

      arr.sort(function (a, b) {
        return b - a
      })

      console.log(arr)
    </script>
  </head>
  <body></body>
</html>
```

## 84\_函数

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      function fn() {
        /*
         *   除了this外，函数中还有一个隐含的参数叫做arguments
         *       arguments 是一个类数组对象（伪数组）
         *           类数组对象和数组的操作方式基本一致，
         *               只是不能调用数组的方法
         *
         *       在函数执行时，所有的实参都会存储在arguments对象中,
         *           通过arguments，即使不定义形参也可以使用实参
         * */
        // console.log(Array.isArray(arguments));
        console.log(arguments[1])
      }

      // fn('hello', true, 123);

      // 创建一个函数，可以求任意个数字的和
      function sum() {
        // 创建一个变量，存储结果
        let result = 0
        // 遍历arguments
        for (let i = 0; i < arguments.length; i++) {
          result += arguments[i]
        }
        return result
      }

      // console.log(sum(123, 456));
    </script>
  </head>
  <body></body>
</html>
```

## 85\_函数

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      function fn(a, b) {
        /*
         *   根据函数的调用方式不同，this的值也不同：
         *       1.以函数形式调用，this是window
         *       2.以方法形式调用，this调用方法的对象
         *       3.以构造函数形式调用，this是新建的对象
         *       4.通过call和apply调用函数时，第一个参数是谁this就是谁
         * */
        // alert(this);
        // alert('函数执行了~~');
        console.log(a, b)
      }

      let obj = { fn }

      // fn();
      // obj.fn();
      // new fn();
      /*
       *   函数对象的方法：
       *       call()
       *           - 当我们调用call()方法时，实际上和直接调用函数的效果类似。
       *           - call可以用来指定函数的this，它的第一个参数传谁函数的this就是谁
       *           - call()传递实参时，直接从第二个参数开始一一传递
       *       apply()
       *           - apply()的作用和call一样
       *           - apply需要将实参保存到一个类数组对象中同一传递
       *
       * */
      // fn.call('hello');
      // fn.apply(window);

      // obj.fn.call(window, 123, 456);
      obj.fn.apply(window, [123, 456])
    </script>
  </head>
  <body></body>
</html>
```

## 86\_递归

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   创建一个函数，用来求任意数的阶乘
       *       6! = 1 x 2 x 3 x 4 x 5 x 6
       * */
      function jieCheng(num) {
        // 创建一个变量来存储结果
        let result = 1
        for (let i = 2; i <= num; i++) {
          result *= i
        }
        return result
      }
      console.log(jieCheng(6))

      /*
       *   递归的核心思想在于将一个大的问题拆分为小的，从而解决问题
       *       递归就是函数自己调用自己，它的作用和循环基本上一致
       *       递归能做事循环也能做，循环能做的事递归也许，而且循环的性能其实更好
       *       递归的好处，思路比较简单，代码比较容易理解
       *
       *   求 6!
       *       6! = 5! x 6
       *       5! = 4! x 5
       *       4! = 3! x 4
       *       3! = 2! x 3
       *       2! = 1! x 2
       *       1! = 1
       * */

      /*
       *   求num的阶乘
       *
       *       6的阶乘
       *           jieCheng2(6) --> 6 * jieCheng2(5)
       *           jieCheng2(5) --> 5 * jieCheng2(4)
       *           jieCheng2(4) --> 4 * jieCheng2(3)
       *           jieCheng2(3) --> 3 * jieCheng2(2)
       *           jieCheng2(2) --> 2 * jieCheng2(1)
       *           jieCheng2(1) --> 1
       * */
      function jieCheng2(num) {
        // 1.基线条件，递归停止的条件
        if (num === 1) {
          return 1
        }
        // 2.递归条件，如何对问题进行拆分
        // 6! = 5! * 6
        // num! = (num - 1) * num
        return num * jieCheng2(num - 1)
      }

      // console.log(jieCheng2(10));

      /*
       *   一对兔子，年龄超过两个月后，每个月生一对兔子
       *       创建一个函数，求n个月后有多少对兔子
       *
       *   创建一个函数计算斐波那契数列：
       *       1 1 2 3 5 8 13 21 34 55 ...
       * */

      /*
       *   创建函数，用来获取斐波那契数列的第 num 个数字
       * */
      function fib(num) {
        // 基线条件
        if (num < 3) {
          return 1
        }
        //num-1  num-2
        return fib(num - 1) + fib(num - 2)
      }

      /*
       *
       * 快速排序（quick sort）
       *   [5,1,3,4,9,7,8,6,2]
       *   - 思路：
       *       1.先从数组提取一个基数
       *           5
       *       2.创建两个数组，一个叫做left，一个叫right
       *           left = []   right = []
       *       3.将数组中的每一个值和基数进行比较
       *           比基数大的，放入到right；
       *           比基数小的，放入到left
       *           left = [1,3,4,2]   right = [9,7,8,6]
       *           [1,3,4,2] 5 [9,7,8,6]
       *       4.对left和right两个数组继续重复上述步骤
       *
       *
       * */
      let arr = [5, 1, 3, 4, 9, 7, 8, 6, 2]
    </script>
  </head>
  <body></body>
</html>
```

# day09

## 87\_复习

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      let arr = [1, 2, 3]
      // arr.forEach()

      // 类似于 ...args 被称为剩余参数，剩余参数它会获取到所有的没有形参对应的实参
      /*
       *   ...args 表示剩余参数，它和arguments的区别：
       *       1.剩余参数就是一个数组，可以调用数组的方法
       *       2.args只会保存没有形参对应的参数
       *       3.剩余参数必须是参数列表中的最后一个
       *
       * */
      function fn(a, b, ...args) {
        console.log(args)
      }

      // fn(10, 20, 30, 40, 50);

      let obj = { name: '孙悟空' }

      function fn2() {
        console.log(this)
      }

      // fn2.call(obj);

      /*
       *   bind()也是一个函数的方法，调用方法时bind会返回一个新的函数对象
       *       这个新的函数对象的功能和原来函数的功能是一样的，不同点在于新函数的this是设置死的
       * */
      let fn3 = fn2.bind(obj)

      // console.log(fn3);
      fn3()
    </script>
  </head>
  <body></body>
</html>
```

## 88\_快速排序

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      let nums = [5, 1, 3, 4, 9, 7, 8, 6, 2]

      /*
       *   定义一个函数用来对一个数组进行快速排序
       * */
      function quickSort(arr) {
        // 设置基线条件，什么时候不需要排序
        if (arr.length < 2) {
          return arr
        }

        // arr是要排序的数组
        // 获取一个基准值
        let basis = arr[0]

        // 创建两个数组
        let left = [] // 放左值
        let right = [] // 放右值

        //将数组中的值和基准值进行比较
        for (let i = 1; i < arr.length; i++) {
          if (arr[i] < basis) {
            // 将小于基准值的值，放入到left中
            left.push(arr[i])
          } else {
            // 将大于或等于基准值的值，放入到right中
            right.push(arr[i])
          }
        }

        return quickSort(left).concat(basis, quickSort(right))
      }

      console.log(quickSort(nums))
    </script>
  </head>
  <body></body>
</html>
```

## 89_Math

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*

            Math
                - Math不是一个构造函数，不能用来创建对象
                - Math中包含了一些数学相关的常量或方法
                - Math我们成其为是一种 工具类
                - 属性：
                    Math.PI 表示圆周率

                - 方法：
                    Math.abs()
                        - 用来求一个数的绝对值
                    Math.ceil()
                        - 用来对一个数进行向上取整
                    Math.floor()
                        - 用来对一个数进行向下取整
                    Math.round()
                        - 用来对一个数进行四舍五入取整
                    Math.max()
                    Math.min()
                        - 获取多个值中的较大或较小值
                    Math.pow(x, y)
                        - 求x的y次幂
                    Math.sqrt()
                        - 对一个数进行开方
        */

      // console.log(Math.PI);
      // console.log(Math.abs(-10));

      // console.log(Math.ceil(3.1));
      // console.log(Math.ceil(-3.1));
      // console.log(Math.floor(3.9));
      // console.log(Math.floor(-3.9));

      // console.log(Math.round(4.5));
      // console.log(Math.min(3,1,4,5,100));
      // console.log(Math.max(3,1,4,5,100));

      // console.log(Math.pow(2, 3));
      // console.log(Math.sqrt(9));

      /*
       *
       * Math.random() 用来生成一个 0-1之间的随机数
       *   生成一个 0-x之间的随机数
       *       Math.round(Math.random() * x)
       *   生成一个 x-y之间的随机数
       *       Math.round(Math.random() * (y-x))+x
       *
       **/
      for (let i = 0; i < 100; i++) {
        // 生成一个0-5之间的随机数
        // console.log(Math.round(Math.random() * 5));
        // 生成一个1-6之间的随机数
        // 生成一个5-8之间的随机数
        // console.log(Math.round(Math.random() * 3)+5);
      }

      let arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12]

      arr.sort(function (a, b) {
        return Math.random() - Math.random()
      })

      console.log(arr)
    </script>
  </head>
  <body></body>
</html>
```

## 90\_排序的性能

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*创建两数组*/
      let arr1 = []
      let arr2 = []

      /*随机向数组中添加元素*/
      for (let i = 0; i < 1000000; i++) {
        // 生成一个随机数
        let num = Math.round(Math.random() * 10000)
        // 将num添加到数组中
        arr1.push(num)
        arr2.push(num)
      }

      let begin = Date.now()
      // console.time('快速排序');
      quickSort(arr1)
      // console.timeEnd('快速排序');
      let end = Date.now()

      console.log(end - begin)

      // console.time('sort');
      // arr2.sort(function (a, b) {
      //     return a-b;
      // });
      // console.timeEnd('sort');

      // console.time('冒泡排序');
      // bubbleSort(arr2);
      // console.timeEnd('冒泡排序');

      // let arr3 = [];
      //
      // for(let i=0; i<10000; i++){
      //     arr3.push(i);
      // }
      //
      // console.log(arr3);

      function quickSort(arr) {
        if (arr.length < 2) {
          return arr
        }
        // 随机获取一个index
        let basisIndex = Math.floor(Math.random() * arr.length)
        let basis = arr[basisIndex]
        let left = [] // 放左值
        let right = [] // 放右值
        for (let i = 0; i < arr.length; i++) {
          // 判断是不是基准值自己
          if (i === basisIndex) {
            continue
          }
          if (arr[i] < basis) {
            left.push(arr[i])
          } else {
            right.push(arr[i])
          }
        }
        return quickSort(left).concat(basis, quickSort(right))
      }

      function bubbleSort(arr) {
        for (let j = 0; j < arr.length - 1; j++) {
          // 遍历数组，获取到所有的元素
          for (let i = 0; i < arr.length - 1 - j; i++) {
            //当前数 arr[i]   后边数 arr[i+1]
            // console.log(arr[i], arr[i+1]);
            if (arr[i] > arr[i + 1]) {
              // 前边的数字大于后边的数字，需要交换两个元素的位置
              let temp = arr[i]
              arr[i] = arr[i + 1]
              arr[i + 1] = temp
            }
          }
        }
        return arr
      }
    </script>
  </head>
  <body></body>
</html>
```

## 91_Date

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   Date
       *       - JS中所有的日期相关的数据都通过Date来表示
       *       - 如果直接创建Date对象，则会创建一个表示当前时间的对象
       *       - 方法：
       *
       *
       * */

      // 创建一个表示当前日期的对象
      let d = new Date()

      // 创建一个表示指定日期的对象
      // 日期字符串的格式 '月/日/四位年 时:分:秒'
      d = new Date('12/30/2019 14:33:58')

      /*
            getDay() 获取当前日期对象是周几
                返回值是 0-6
                        0表示周日
                        1表示周一
            getDate() 获取当前日期
            getMonth() 获取当前是几月
                返回值 0-11
                    0 表示 1月
                    1 表示 2月
                    ...
            getFullYear() 获取四位年份
          */
      let weekName = ['周日', '周一', '周二', '周三', '周四', '周五', '周六']
      let day = d.getDay()
      let dt = d.getDate()
      let month = d.getMonth()
      d = new Date()

      let year = d.getFullYear()
      // console.log(weekName[day]);
      // console.log(month);
      // console.log(year);

      /*
            getTime()
                - 用来获取当前日期对象的时间戳
                - 时间戳是自1970年1月1日0时0分0秒，到现在时间所经历的毫秒
                - 在计算机底层所有的时间都是以时间戳的形式存储

            Date.now()
                - 获取当前的时间戳
        * */
      let time = d.getTime()

      console.log(time)
    </script>
  </head>
  <body></body>
</html>
```

## 92\_包装类

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       * 包装类
       *   - 在JS中，给我们提供了包装类
       *       String
       *       Number
       *       Boolean
       *       通过这三个包装类，可以直接创建String类型的Number类型的和Boolean类型对象
       *       包装类并不是提供给我们创建对象用的，而是JS自己留着用
       * */

      // let num = 10;
      // 以下这些写法，在实际开发中 绝对不要出现
      // let num = new Number(10);
      // let num2 = new Number(10);
      // let str = new String('Hello');
      // let bool = new Boolean(true);
      // alert(num === num2);

      let num = 10

      /*
       *   当我们调用一个基本数据类型的属性或方法时，
       *       浏览器会通过包装类临时将其转换为对象，然后调用对象的属性或方法
       *
       * */
    </script>
  </head>
  <body></body>
</html>
```

## 93\_字符串

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      let str = 'hello' //['h','e','l','l','o']

      /*
            字符串
                - 字符串本质上就是一个字符数组
                - 你在操作字符串时，完全可以将字符串想象为是一个数组
                - 属性：
                    length 获取字符串的长度
                - 方法：
                    concat()
                        - 用来检查两个或多个字符串连接为一个字符串
                    charAt()
                        - 根据索引获取字符串中的字符串
                    charCodeAt()
                        - 根据索引获取指定字符的字符编码
                    String.fromCharCode()
                        - 根据编码返回字符
                    indexOf()
                    lastIndexOf()
                        - 查找一个字符串中是否含有指定的子串
                    slice()
                        - 用来从一个字符串中截取一个子串
                    split()
                        - 用来将一个字符串拆分为一个数组
                        - 参数：
                            需要一个分隔符作为参数
                                会根据分隔符去拆分字符串
                    toLowerCase()
                        - 将字符串转换为小写
                    toUpperCase()
                        - 将字符串转换为大写
                    trim()
                        - 去除字符串的前后空格
                    trimEnd()
                        - 去除字符串后的空格
                    trimStart()
                        - 去除字符串前的空格
                    endsWith()
                        - 检查一个字符串是否以指定内容结尾
                    statsWith()
                        - 检查一个字符串是否以指定内容开头

        * */

      let result = str.concat('world')

      str = 'hello'
      result = str.charAt(0)
      result = str.charAt(1)
      result = str.charCodeAt(1)
      str = '今天天气真不错！'
      result = str.charCodeAt(6)

      str = 'Hello Atguigu!'

      result = str.indexOf('g')
      result = str.lastIndexOf('g')
      result = str.indexOf('g', 9)
      result = str.indexOf('lo')
      result = str.indexOf('hlo')

      str = 'Hello Atguigu!'
      result = str.slice(6, 8)
      result = str.slice(1, -1)

      str = 'a,b,c,d,e,f'
      result = str.split(',')
      result = str.split('d')
      result = str.split('')

      str = 'abcdEFG'
      let str2 = 'abcdefg'

      result = str.toLowerCase()
      result = str.toUpperCase()

      // console.log(str.toUpperCase() === str.toUpperCase());

      str = '       admin      '
      result = str.trim()
      result = str.trimEnd()
      result = str.trimStart()

      str = 'hello hello how are you'

      result = str.endsWith('you')
      result = str.startsWith('you')

      console.log(result)
    </script>
  </head>
  <body></body>
</html>
```

## 94\_解构赋值

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   1.将数组中元素赋值给变量
       *       let [变量1,变量2,...变量n,] = 数组;
       *   2.将数组中的元素拆分作为参数传递
       *       fn(...数组);
       *   3.对对象的解构
       *       let {变量1, 变量2} = 对象;
       * */

      let arr = [1, 2, 3, 4, 5, 6, 7]
      let [a, b, ...c] = arr

      // console.log('a =', a);
      // console.log('b =', b);
      // console.log('c =', c);

      // let temp = arr[1];
      // arr[1] = arr[2];
      // arr[2] = temp;
      ;[arr[1], arr[2]] = [arr[2], arr[1]]

      // console.log(arr);

      function sum(a, b, c) {
        return a + b + c
      }

      let arr2 = [567, 765, 345]

      // console.log(sum(...arr2));

      let obj = { name: '孙悟空', age: 18, gender: '男' }

      let { name, age } = obj

      console.log(name, age)
    </script>
  </head>
  <body></body>
</html>
```

## 95\_箭头函数

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       *   语法：
       *       ([参数列表]) => 返回值
       *
       *       参数 => 返回值
       *
       *       ([参数列表]) => {
       *           语句...
       *       }
       *
       *   注意：
       *       箭头函数中的this在函数创建时就以确定,
       *           它由外层函数（作用域）中的this来决定
       *           外层的this是谁，它的this就是谁
       *
       * */

      let sum = (a, b) => a + b
      // console.log(sum(123, 456));

      let arr = ['孙悟空', '猪八戒', '沙和尚']
      // arr.forEach(element=>console.log(element));

      let arr2 = [3, 4, 1, 2, 5]
      arr2.sort((a, b) => a - b)
      // console.log(arr2);

      let sum2 = (a, b) => {
        console.log('hello')
        console.log('你好')
        return a + b
      }
      // sum2(123,456);

      let fn = () => ({ name: '孙悟空' })

      // fn();

      let fn2 = () => alert(this) // window

      let obj = {
        fn2: fn2,

        test: function () {
          let fn = () => alert(this)

          fn()
        },
      }

      obj.fn2()
      // obj.test();
    </script>
  </head>
  <body></body>
</html>
```

## 96\_闭包

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*

            闭包：
                闭包就是能访问到外部函数中变量的内部函数

            用途：
                闭包主要用来藏起一些不希望被别人看到的东西

            闭包构成要件：
                1. 闭包必须有函数的嵌套
                2. 内部函数必须要访问外部函数的变量
                3. 必须将内部函数作为返回值返回


             闭包的生命周期：
                当外部函数调用时，闭包便产生了
                    外部函数每调用一次就会产生一个闭包
                当内部函数被垃圾回收时，闭包销毁



        * */
      function outer() {
        // 定义一个变量，记录函数执行的次数
        let times = 0
        // 创建一个函数，函数每次调用时，都会打印函数被调用的次数
        function inner() {
          times++
          alert(times)
        }
        // 将inner设置为函数的返回值
        return inner
      }

      let fn = outer()
      let fn2 = outer()
      let fn3 = outer()

      fn = null
      fn2 = null
      fn3 = null

      // function f() {
      //     let a = 10;
      //     function f1() {
      //         console.log(a);
      //     }
      //     return f1;
      // }

      let fn4 = (function () {
        let times = 0

        return function () {
          alert(++times)
        }
      })()
    </script>
  </head>
  <body></body>
</html>
```

## 97_DOM

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
            DOM(Document Object Model)
                - 文档对象模型
                    文档（Document）
                        - 文档指整个网页
                    对象（Object）
                        - DOM将网页中的所有的东西都转换为了对象
                    模型（Model）
                        - 模型用来体现节点之间的关系

                - 网页由三个部分组成：
                    结构（HTML）
                    表现（CSS）
                    行为（JavaScript）
                - DOM中为我们提供了大量的对象，使我们可以通过JS来完成对网页操控

                - 节点（Node）
                    - 网页中的所有部分都可以称为使一个节点，虽然都是节点，但是有着不同的类型
                        - 文档节点
                            - 表示整个网页
                        - 元素节点
                            - 各种标签都属于元素节点
                        - 属性节点
                            - 标签中的属性称为属性节点
                        - 文本节点
                            - 标签中的文字


        */
    </script>
  </head>
  <body>
    <button id="btn">我是一个按钮</button>
    <script>
      // 通过JS来修改button按钮
      // document 对象表示整个网页，它由浏览器提供可以直接使用
      let btn = document.getElementById('btn')
      btn.innerHTML = "I'm Button"
    </script>
  </body>
</html>
```

# day10

## 98\_复习

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      let a = { x: 10 }
      let b = a

      // 连着使用两个等会对变量进行赋值时，赋值时同时完成
      a.x = a = { n: 20 }

      /*
       *   a.x = {n:20}
       *   a = {n:20}
       * */

      // console.log(a.x);
      // console.log(b.x);

      // let str = 'hello hello'; // abc --> cba
      // let result = str.split('');
      // result.reverse();
      // str = result.join('');

      let str = 'hello hello'
      str = str.split('').reverse().join('')

      console.log(str)
    </script>
  </head>
  <body></body>
</html>
```

## 99_DOM

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
  </head>
  <body>
    <!--
    可以直接在元素中设置事件的响应
-->
    <!--<button onmouseenter="alert('哈哈！');" id="btn">我是一个按钮</button>-->
    <button id="btn">我是一个按钮</button>

    <script>
      /*let btn = document.getElementById('btn');
    btn.innerHTML = '😄';*/
      /*
       *   事件（event）
       *       - 事件就是用户和网页的交互瞬间
       *           例如：点击鼠标，点击按钮，鼠标移动，键盘按下 ...
       *       - 我们通过响应用户的事件来完成和用户的交换
       * */

      // 在script标签中，通过js代码来设置事件的响应
      let btn = document.getElementById('btn')
      // 可以通过为指定对象的事件属性设置响应函数的形式来处理事件
      // 在事件发生时触发的函数称为事件的响应函数
      btn.onclick = function () {
        alert('Hello')
      }
    </script>
  </body>
</html>
```

## 100\_文档的加载

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      /*
       * 网页中的代码在加载时，是自上向下一行一行加载的，
       *   如果将script标签写在页面的上边，此时js代码会优先于网页中元素加载，
       *   所以会出现无法正常获取到DOM对象的情况出现
       *
       * 为了解决问题：
       *   1.可以直接将js代码写在body的下边
       *   2.也可以将js代码编写到window.onload的回调函数
       *   3.如果是外部文件，可以在引入时在script标签添加defer属性使其延迟加载
       *
       * */

      // window.onload事件会在网页加载完毕之后触发
      window.onload = function () {
        // 获取id为btn的按钮
        let btn = document.getElementById('btn')
        btn.onclick = function () {
          alert('嘻嘻！')
        }
      }
    </script>
  </head>
  <body>
    <button id="btn">点我一下</button>

    <!--<script>-->
    <!--    let btn = document.getElementById('btn');-->
    <!--    alert(btn);-->
    <!--</script>-->
  </body>
</html>
```

## 101\_文档加载

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <!--
        如果引入外部文件js文件时，在script标签上设置defer，
            则js文件会在网页加载完毕之后才加载
    -->
    <script defer src="app.js"></script>
  </head>
  <body>
    <button id="btn">我是一个按钮</button>
  </body>
</html>
```

## 102_DOM 查询

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>DOM查询</title>
    <style>
      * {
        margin: 0;
        padding: 0;
      }

      #box1 {
        width: 100px;
        height: 100px;
        background-color: yellowgreen;
        margin: 10px;
      }
    </style>
    <script>
      /*
            如何获取到我们想要对象？
        * */

      window.onload = function () {
        // 当我们点击按钮时，可以获取到box1

        // 获取按钮btn01
        let btn01 = document.getElementById('btn01')
        // 为btn01绑定一个单击响应函数
        btn01.onclick = function () {
          /*
           * document.getElementById()
           *   - 根据id获取一个元素节点对象
           * */

          // 获取到id为box1的div
          let box1 = document.getElementById('box1')

          // alert(box1);
          box1.innerHTML = '我是box1中的文字'
        }

        // 当点击按钮2时可以获取到所有的class为item的li
        // 获取到按钮2的对象
        let btn02 = document.getElementById('btn02')
        btn02.onclick = function () {
          /*
           * document.getElementsByClassName()
           *   - 根据class属性值获取一组元素
           * */
          // 获取class为item的元素
          // let items = document.getElementsByClassName('item');

          // document.getElementsByTagName() 根据标签名来获取一组元素节点对象
          let items = document.getElementsByTagName('li')
          // 遍历items
          for (let i = 0; i < items.length; i++) {
            alert(items[i].innerHTML)
          }
        }

        // 获取btn03
        let btn03 = document.getElementById('btn03')
        btn03.onclick = function () {
          /*
           * getElementsXxx一系列总会返回一个类数组对象
           * */

          // let divs = document.getElementsByTagName('div');
          // alert(divs.length);

          // document.getElementsByTagName('*') 用来获取页面中的所有元素
          // let all = document.getElementsByTagName('*');
          // for(let i=0; i<all.length; i++){
          //     alert(all[i]);
          // }

          /*
           * document.getElementsByName()
           *   - 根据name属性值获取一组元素节点对象
           *       (主要用来对付表单项)
           *
           * */
          let um = document.getElementsByName('username')[0]
          let genders = document.getElementsByName('gender')

          // alert(um);

          // innerHTML用来获取或设置标签内部的HTML代码

          for (let i = 0; i < genders.length; i++) {
            // 读取一个对象的属性值 value
            /*
             *   读取哪个属性就.哪个
             *   特殊的就是 class属性，需要通过 className来获取
             *   classList 返回的是当前类所有class的列表，可以通过索引来获取具体的class
             * */
            alert(genders[i].classList[0])
          }
        }

        // 为btn04绑定单击响应函数
        let btn04 = document.getElementById('btn04')
        btn04.onclick = function () {
          // 获取name为username的input
          console.log(document.getElementsByName('username'))
          let um = document.getElementsByName('username')[0]
          // 修改对象的属性 对象.属性 = 值
          // alert(um.value);
          um.value = '今天天气真不错！'
        }
      }
    </script>
  </head>
  <body>
    <button id="btn01">按钮一</button>
    <button id="btn02">按钮二</button>
    <button id="btn03">按钮三</button>
    <button id="btn04">按钮四</button>

    <div id="box1"></div>

    <ul>
      <li class="item">列表1</li>
      <li class="item">列表2</li>
      <li class="item">列表3</li>
      <li class="item">列表4</li>
    </ul>

    <form action="#">
      用户名：<input type="text" name="username" /> <br />
      性别：<input class="hello abc bcd" type="radio" name="gender" value="male" />男
      <input class="hello abc bcd" type="radio" name="gender" value="female" />女
    </form>
  </body>
</html>
```

## 103\_练习

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>图片浏览器</title>
    <style>
      * {
        padding: 0;
        margin: 0;
      }

      .outer {
        width: 500px;
        margin: 50px auto;
        text-align: center;
        padding: 10px;
        background-color: greenyellow;
      }
    </style>
    <script>
      /*
       * 点击按钮切换图片
       * */
      window.onload = function () {
        // 获取两个按钮对象
        let prev = document.getElementById('prev')
        let next = document.getElementById('next')
        // 获取img标签
        let img = document.getElementsByTagName('img')[0]
        // 创建一个数组，用来存储图片的路径
        let imgPath = ['img/1.jpg', 'img/2.jpg', 'img/3.jpg', 'img/4.jpg', 'img/5.jpg']
        // 创建一个变量，表示当前正显示的图片
        let index = 0
        // 获取id为info的p元素
        let info = document.getElementById('info')
        // 设置info中的文字
        info.innerHTML = '当前第' + (index + 1) + '张，共' + imgPath.length + '张'

        // 为上一张绑定响应函数
        prev.onclick = function () {
          // 使索引自减
          index--

          //判断，index是否超出范围
          if (index < 0) {
            index = imgPath.length - 1
          }

          img.src = imgPath[index]

          // 设置info中的文字
          info.innerHTML = '当前第' + (index + 1) + '张，共' + imgPath.length + '张'
        }

        // 为下一张的按钮绑定响应函数
        next.onclick = function () {
          // 使索引自增
          index++
          //判断，index是否超出范围
          if (index > imgPath.length - 1) {
            index = 0
          }

          // 修改img的src属性
          img.src = imgPath[index]

          // 设置info中的文字
          info.innerHTML = '当前第' + (index + 1) + '张，共' + imgPath.length + '张'
        }
      }
    </script>
  </head>
  <body>
    <!--创建一个外部容器-->
    <div class="outer">
      <p id="info">当前第1张，共5张</p>
      <img src="img/1.jpg" alt="图片" />
      <button id="prev">上一张</button>
      <button id="next">下一张</button>
    </div>
  </body>
</html>
```

## 104_DOM 查询

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      window.onload = function () {
        /*
         * 在document提供了一些直接获取元素的方法
         *   document.body 获取到页面的body元素
         *   document.documentElement 获取页面中html根元素
         * */

        // let body = document.getElementsByTagName('body')[0];

        // alert(document.all.length);

        // alert(document.body);
        // alert(document.documentElement);

        /*
            document.querySelector()
                - 根据CSS选择器来获取一个元素节点
                - 需要一个选择器的字符串作为参数，会根据选择器去页面中获取元素
                    该方法只会返回符合条件的第一个元素
            querySelectorAll()
                - 根据CSS选择器返回所有符合条件的元素节点
            */
        let div = document.querySelector('div[title]')

        // alert(div);
        // div.innerHTML = '这是被我找到的div';

        let item = document.querySelector('.item')
        // alert(items);
        item.innerHTML = '我变了！'

        let items = document.querySelectorAll('.item')
        alert(items.length)
      }
    </script>
  </head>
  <body>
    <div title="我是一个div">我是一个div</div>

    <div>我是一个div</div>

    <ul>
      <li class="item">选项1</li>
      <li class="item">选项2</li>
      <li class="item">选项3</li>
      <li class="item">选项4</li>
    </ul>
  </body>
</html>
```

## 105_DOM 查询

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <style>
      #box1 {
        background-color: tomato;
      }

      #p1 {
        background-color: skyblue;
      }
    </style>
    <script>
      window.onload = function () {
        // 为btn01绑定一个单击响应函数
        document.getElementById('btn01').onclick = function () {
          // let p = document.querySelectorAll('#box1 p');
          // alert(p.length);

          // 获取id为box1的元素
          let box1 = document.getElementById('box1')
          // 获取box1中的所有p元素
          let p = box1.getElementsByTagName('p')

          for (let i = 0; i < p.length; i++) {
            p[i].innerHTML += '哈哈~'
          }
        }

        // 为btn02绑定一个单击响应函数
        document.getElementById('btn02').onclick = function () {
          // 获取box1
          let box1 = document.getElementById('box1')
          // 获取box1的所有子节点
          //childNodes 表示当前元素的所有子节点
          //  空白的文本节点也会被当成子节点返回
          let cns = box1.childNodes

          // children 用来获取当前元素的所有子元素
          let cr = box1.children

          alert(cr.length)
          // for(let i=0; i<cns.length; i++){
          //     alert(cns[i]);
          // }
        }

        document.getElementById('btn03').onclick = function () {
          let box1 = document.getElementById('box1')
          // firstChild 用来获取当前元素的第一个子节点
          // firstElementChild 用来获取第一个子元素
          let fc = box1.firstChild
          let fec = box1.firstElementChild

          // box1.lastChild 最后一个子节点
          // box1.lastElementChild 最后一个子元素

          alert(fec)
        }

        document.getElementById('btn04').onclick = function () {
          // 获取id为p1的元素的父节点
          let p1 = document.getElementById('p1')

          // parentNode 用来获取当前元素的父节点（通常都是元素）
          // alert(p1.parentNode);

          // previousSibling 获取当前节点的前一个兄弟节点
          // previousElementSibling 获取当前节点上一个兄弟元素
          // nextSibling 获取下一个兄弟节点
          // nextElementSibling 获取下一个兄弟元素
          let ps = p1.previousSibling
          let pes = p1.previousElementSibling

          alert(pes.innerHTML)
        }

        document.getElementById('btn05').onclick = function () {
          // 读取标签内部的html代码
          let p1 = document.getElementById('p1')
          // innerHTML 表示标签内部的HTML代码（包含标签的）
          // alert(p1.innerHTML);
          // innerText 表示标签内部的文本内容（不含标签）
          // alert(p1.innerText);
          // alert(p1.textContent);

          //        <p id="p1">段落2</p>
          let text = p1.firstChild
          // alert(text.nodeValue);

          alert(p1.firstChild.nodeValue)
        }
      }
    </script>
  </head>
  <body>
    <button id="btn01">按钮1</button>
    <button id="btn02">按钮2</button>
    <button id="btn03">按钮3</button>
    <button id="btn04">按钮4</button>
    <button id="btn05">按钮5</button>

    <div id="box1">
      <p>段落1</p>
      <p>段落2</p>
      <p>段落3</p>
    </div>

    <div>
      <p>段落1</p>
      <p id="p1">段落2</p>
      <p>段落3</p>
    </div>
  </body>
</html>
```

## 106\_练习 1

```html
﻿<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>全选练习</title>
    <script></script>
  </head>
  <body>
    <form method="post" action="">
      你爱好的运动是？<input type="checkbox" id="checkedAllBox" />全选/全不选

      <br />
      <input type="checkbox" name="items" value="足球" />足球
      <input type="checkbox" name="items" value="篮球" />篮球
      <input type="checkbox" name="items" value="羽毛球" />羽毛球
      <input type="checkbox" name="items" value="乒乓球" />乒乓球
      <br />
      <input type="button" id="checkedAllBtn" value="全　选" />
      <input type="button" id="checkedNoBtn" value="全不选" />
      <input type="button" id="checkedRevBtn" value="反　选" />
      <input type="button" id="sendBtn" value="提　交" />
    </form>
  </body>
</html>
```

# day11

## 107\_练习 1

```html
﻿<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>全选练习</title>
    <script>
      window.onload = function () {
        /*
         * 	1.全选按钮
         * 	- 点击全选按钮后，四个多选框变成选中状态
         * */
        // 获取全选按钮
        let checkedAllBtn = document.getElementById('checkedAllBtn')
        // 为它绑定单击响应函数
        checkedAllBtn.onclick = function () {
          // 获取四个多选框
          let items = document.getElementsByName('items')
          // 将它们变成选中状态
          for (let i = 0; i < items.length; i++) {
            // 多选框的checked属性用来设置或读取它的选中状态
            // 它需要一个布尔值，如果是true，则选中，false则不选中
            items[i].checked = true
          }
        }
      }
    </script>
  </head>
  <body>
    <form method="post" action="">
      你爱好的运动是？<input type="checkbox" id="checkedAllBox" />全选/全不选

      <br />
      <input type="checkbox" name="items" value="足球" />足球
      <input type="checkbox" name="items" value="篮球" />篮球
      <input type="checkbox" name="items" value="羽毛球" />羽毛球
      <input type="checkbox" name="items" value="乒乓球" />乒乓球
      <br />
      <input type="button" id="checkedAllBtn" value="全　选" />
      <input type="button" id="checkedNoBtn" value="全不选" />
      <input type="button" id="checkedRevBtn" value="反　选" />
      <input type="button" id="sendBtn" value="提　交" />
    </form>
  </body>
</html>
```

## 108\_练习 1

```html
﻿<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>全选练习</title>
    <script>
      window.onload = function () {
        /*
         * 	1.全选按钮
         * 	- 点击全选按钮后，四个多选框变成选中状态
         * */
        // 获取全选按钮
        let checkedAllBtn = document.getElementById('checkedAllBtn')
        // 获取四个多选框
        let items = document.getElementsByName('items')

        // 为它绑定单击响应函数
        checkedAllBtn.onclick = function () {
          // 将它们变成选中状态
          for (let i = 0; i < items.length; i++) {
            // 多选框的checked属性用来设置或读取它的选中状态
            // 它需要一个布尔值，如果是true，则选中，false则不选中
            items[i].checked = true
          }

          // 全选
          checkedAllBox.checked = true
        }

        /*
         *  点击全不选按钮后，所有选择框变成没选中的状态
         * */
        // 为全不选按钮绑定一个单击响应函数
        let checkedNoBtn = document.getElementById('checkedNoBtn')
        checkedNoBtn.onclick = function () {
          // 遍历items
          for (let i = 0; i < items.length; i++) {
            items[i].checked = false
          }

          // 全不选
          checkedAllBox.checked = false
        }

        /*
         * 反选按钮
         * 	- 点击按钮后，选中的变成没选中，没选中变成选中
         * */
        let checkedRevBtn = document.getElementById('checkedRevBtn')
        checkedRevBtn.onclick = function () {
          // 遍历items
          for (let i = 0; i < items.length; i++) {
            items[i].checked = !items[i].checked
            /*if(items[i].checked){
					items[i].checked = false;
				}else{
					items[i].checked = true;
				}*/
          }
        }

        /*
         * 提交按钮：
         * 	- 点击按钮后弹出被选中的内容
         * */
        // 为提交按钮绑定单击响应函数
        let sendBtn = document.getElementById('sendBtn')
        sendBtn.onclick = function () {
          //遍历items
          for (let i = 0; i < items.length; i++) {
            if (items[i].checked) {
              alert(items[i].value)
            }

            // items[i].checked && alert(items[i].value);
          }
        }

        /*
         * 全选/全不选的多选框
         * 	- 使四个小多选框和大多选框进行状态同步
         * */
        // 为全选/全不选的多选框绑定单击响应函数
        let checkedAllBox = document.getElementById('checkedAllBox')
        checkedAllBox.onclick = function () {
          // alert(this.id);
          // 在事件的响应函数中，this就是绑定事件的对象
          // 设置items状态
          for (let i = 0; i < items.length; i++) {
            items[i].checked = this.checked
          }
        }

        /*
         * 	使大多选框的状态和小多选框的状态进行同步，
         * 		四个全选中了，大的也选中
         * 		四个中有没选的，大的也不选
         * */

        // 分别为四个小多选框绑定响应函数
        for (let i = 0; i < items.length; i++) {
          items[i].onclick = function () {
            // 定义一个变量来记录状态， 默认为true
            let isAllChecked = true

            // 检查四个多选框是否全都选中
            for (let j = 0; j < items.length; j++) {
              // items[j] 是否被选中
              if (!items[j].checked) {
                // 进入判断，说明当前多选框没有选中，不是全选，将变量设置为false
                isAllChecked = false
                break
              }
            }

            // 修改大多选框的值
            checkedAllBox.checked = isAllChecked
          }
        }
      }
    </script>
  </head>
  <body>
    <form method="post" action="">
      你爱好的运动是？<input type="checkbox" id="checkedAllBox" />全选/全不选

      <br />
      <input type="checkbox" name="items" value="足球" />足球
      <input type="checkbox" name="items" value="篮球" />篮球
      <input type="checkbox" name="items" value="羽毛球" />羽毛球
      <input type="checkbox" name="items" value="乒乓球" />乒乓球
      <br />
      <input type="button" id="checkedAllBtn" value="全　选" />
      <input type="button" id="checkedNoBtn" value="全不选" />
      <input type="button" id="checkedRevBtn" value="反　选" />
      <input type="button" id="sendBtn" value="提　交" />
    </form>
  </body>
</html>
```

## 109\_练习 1

```html
﻿<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>全选练习</title>
    <script>
      window.onload = function () {
        /*
         * 	1.全选按钮
         * 	- 点击全选按钮后，四个多选框变成选中状态
         * */
        // 获取全选按钮
        let checkedAllBtn = document.getElementById('checkedAllBtn')
        // 获取四个多选框
        let items = document.getElementsByName('items')

        // 为它绑定单击响应函数
        checkedAllBtn.onclick = function () {
          // 将它们变成选中状态
          for (let i = 0; i < items.length; i++) {
            // 多选框的checked属性用来设置或读取它的选中状态
            // 它需要一个布尔值，如果是true，则选中，false则不选中
            items[i].checked = true
          }

          // 全选
          checkedAllBox.checked = true
        }

        /*
         *  点击全不选按钮后，所有选择框变成没选中的状态
         * */
        // 为全不选按钮绑定一个单击响应函数
        let checkedNoBtn = document.getElementById('checkedNoBtn')
        checkedNoBtn.onclick = function () {
          // 遍历items
          for (let i = 0; i < items.length; i++) {
            items[i].checked = false
          }

          // 全不选
          checkedAllBox.checked = false
        }

        /*
         * 反选按钮
         * 	- 点击按钮后，选中的变成没选中，没选中变成选中
         * */
        let checkedRevBtn = document.getElementById('checkedRevBtn')
        checkedRevBtn.onclick = function () {
          // 遍历items
          for (let i = 0; i < items.length; i++) {
            items[i].checked = !items[i].checked
          }

          // 获取所有的选中的items
          let checkedItems = document.querySelectorAll('[name=items]:checked')
          // 修改大多选框
          checkedAllBox.checked = checkedItems.length === items.length
        }

        /*
         * 提交按钮：
         * 	- 点击按钮后弹出被选中的内容
         * */
        // 为提交按钮绑定单击响应函数
        let sendBtn = document.getElementById('sendBtn')
        sendBtn.onclick = function () {
          //遍历items
          for (let i = 0; i < items.length; i++) {
            if (items[i].checked) {
              alert(items[i].value)
            }

            // items[i].checked && alert(items[i].value);
          }
        }

        /*
         * 全选/全不选的多选框
         * 	- 使四个小多选框和大多选框进行状态同步
         * */
        // 为全选/全不选的多选框绑定单击响应函数
        let checkedAllBox = document.getElementById('checkedAllBox')
        checkedAllBox.onclick = function () {
          // alert(this.id);
          // 在事件的响应函数中，this就是绑定事件的对象
          // 设置items状态
          for (let i = 0; i < items.length; i++) {
            items[i].checked = this.checked
          }
        }

        /*
         * 	使大多选框的状态和小多选框的状态进行同步，
         * 		四个全选中了，大的也选中
         * 		四个中有没选的，大的也不选
         * */

        // 分别为四个小多选框绑定响应函数
        for (let i = 0; i < items.length; i++) {
          items[i].onclick = function () {
            // 获取所有的选中的items
            let checkedItems = document.querySelectorAll('[name=items]:checked')
            // 判断是否全选
            // let isAllChecked = (checkedItems.length === items.length);
            // 修改大多选框
            checkedAllBox.checked = checkedItems.length === items.length
          }
        }
      }
    </script>
  </head>
  <body>
    <form method="post" action="">
      你爱好的运动是？<input type="checkbox" id="checkedAllBox" />全选/全不选

      <br />
      <input type="checkbox" name="items" value="足球" />足球
      <input type="checkbox" name="items" value="篮球" />篮球
      <input type="checkbox" name="items" value="羽毛球" />羽毛球
      <input type="checkbox" name="items" value="乒乓球" />乒乓球
      <br />
      <input type="button" id="checkedAllBtn" value="全　选" />
      <input type="button" id="checkedNoBtn" value="全不选" />
      <input type="button" id="checkedRevBtn" value="反　选" />
      <input type="button" id="sendBtn" value="提　交" />
    </form>
  </body>
</html>
```

## 110\_创建 DOM 对象

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      window.onload = function () {
        // 点击按钮后，创建一个新的li元素
        document.getElementById('btn01').onclick = function () {
          /*
           *   document.createElement()
           *       - 用来根据标签名来创建一个新元素节点对象
           * */
          // 获取id为list的ul
          let list = document.getElementById('list')
          // 创建一个新的li元素
          let li = document.createElement('li')
          // 创建一个新的文本节点
          let text = document.createTextNode('白骨精')
          // 将text设置为li的子节点
          li.appendChild(text)

          // 将li添加到list中
          // appendChild() 用于向父节点中添加子节点
          // 语法: 父节点.appendChild(子节点);
          list.appendChild(li)

          // alert(li);
        }

        document.getElementById('btn02').onclick = function () {
          // 获取list
          let list = document.getElementById('list')
          // 创建一个li
          let li = document.createElement('li')
          // 设置li中的文本内容
          li.innerHTML = '蜘蛛精'

          list.appendChild(li)
        }
      }
    </script>
  </head>
  <body>
    <button id="btn01">按钮1</button>
    <button id="btn02">按钮2</button>

    <ul id="list">
      <li>孙悟空</li>
      <li>猪八戒</li>
      <li>沙和尚</li>
      <li>唐僧</li>
    </ul>
  </body>
</html>
```

## 111\_插入对象

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      window.onload = function () {
        // 点击按钮后，创建一个新的li元素
        document.getElementById('btn01').onclick = function () {
          // 获取list
          let list = document.getElementById('list')
          // 创建一个li
          let li = document.createElement('li')
          // 设置文本内容
          li.innerHTML = '玉兔精'
          // 将li添加到list中
          // list.appendChild(li);
          // list.insertAdjacentElement('beforeend', li);
          // list.insertAdjacentElement('afterbegin', li);
          /*
           *   insertAdjacentElement
           *       - 用来将一个元素插入到指定元素的指定位置
           *       - 参数：
           *           1.传一个插入的位置
           *               beforebegin 开始标签前
           *               afterbegin 开使标签后（元素的开头）
           *               beforeend  结束标签前（元素的结尾）
           *               afterend 结束标签后
           *           2.被插入的元素
           *
           *  insertAdjacentHTML()
           *       - 在元素的指定位置插入HTML代码
           *  insertAdjacentText()
           *       - 在元素的指定位置插入文本内容
           * */
          // list.insertAdjacentElement('beforebegin', li);
          list.insertAdjacentHTML('afterbegin', '<li>二郎神</li>')
        }

        document.getElementById('btn02').onclick = function () {
          // 获取list
          let list = document.getElementById('list')
          // 获取沙和尚li
          let shs = document.getElementById('shs')
          // 创建一个li
          let li = document.createElement('li')
          // 设置文本内容
          li.innerHTML = '牛魔王'
          // shs.insertAdjacentElement('beforebegin', li);

          /*
           *   将某个元素插入到指定元素的前边
           *       父元素.insertBefore(新节点, 旧节点);
           *           - 将指定节点插入到某节点前边
           *       父元素.replaceChild(新节点, 旧节点);
           *           - 使用新节点替换旧节点
           * */
          // list.insertBefore(li, shs);

          list.replaceChild(li, shs)
        }
      }
    </script>
  </head>
  <body>
    <button id="btn01">按钮1</button>
    <button id="btn02">按钮2</button>

    <!-- beforebegin -->
    <ul id="list">
      <!-- afterbegin -->

      <li>孙悟空</li>
      <li>猪八戒</li>
      <li id="shs">沙和尚</li>
      <li>唐僧</li>

      <!--beforeend-->
    </ul>
    <!--afterend-->
  </body>
</html>
```

## 112\_删除对象

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      window.onload = function () {
        document.getElementById('btn01').onclick = function () {
          // 获取id为list的元素
          // let list = document.getElementById('list');
          // 删除id为shs的元素
          let shs = document.getElementById('shs')

          /*
           *   父节点.removeChild(子节点)
           *       - 用来删除一个子节点
           * */
          // list.removeChild(shs);
          // shs.parentNode.removeChild(shs);
          /*
           *   remove()
           *       - 用来删除当前节点，老版本的浏览器不支持
           * */
          shs.remove()
        }

        document.getElementById('btn02').onclick = function () {
          /*
           *   添加元素时，可以直接通过修改元素innerHTML属性来达到目的,
           *       但是修改innerHTML时，是直接为innerHTML进行重新赋值
           *       这样将会导致其他元素被替换，所以使用innerHTML一定要慎重
           * */
          // 获取list
          let list = document.getElementById('list')

          // list.innerHTML += '<li>白骨精</li>';
          list.insertAdjacentHTML('beforeend', '<li>白骨精</li>')
        }

        document.getElementById('shs').onclick = function () {
          alert('我是真的沙和尚')
        }
      }
    </script>
  </head>
  <body>
    <button id="btn01">按钮1</button>
    <button id="btn02">按钮2</button>
    <ul id="list">
      <li>孙悟空</li>
      <li>猪八戒</li>
      <li id="shs">沙和尚</li>
      <li>唐僧</li>
    </ul>
  </body>
</html>
```

## 113\_练习 2

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <title>添加删除记录练习</title>
    <style>
      #total {
        width: 450px;
        margin-left: auto;
        margin-right: auto;
      }

      ul {
        list-style-type: none;
      }

      li {
        border-style: solid;
        border-width: 1px;
        padding: 5px;
        margin: 5px;
        background-color: #99ff99;
        float: left;
      }

      .inner {
        width: 400px;
        border-style: solid;
        border-width: 1px;
        margin: 10px;
        padding: 10px;
        float: left;
      }

      #employeeTable {
        border-spacing: 1px;
        background-color: black;
        margin: 80px auto 10px auto;
      }

      th,
      td {
        background-color: white;
      }

      #formDiv {
        width: 250px;
        border-style: solid;
        border-width: 1px;
        margin: 50px auto 10px auto;
        padding: 10px;
      }

      #formDiv input {
        width: 100%;
      }

      .word {
        width: 40px;
      }

      .inp {
        width: 200px;
      }
    </style>

    <script>
      window.onload = function () {
        /*
         * 点击超链接后，删除指定员工
         * */

        // 获取所有的超链接
        let links = document.getElementsByTagName('a')
        // 遍历超链接
        for (let i = 0; i < links.length; i++) {
          // 为超链接绑定单击响应函数
          links[i].onclick = function () {
            /*
             * 	点击超链接后，页面会发生跳转这是超链接的默认行为,
             * 		如果不希望默认行为的发生，可以在响应函数的最后
             * 		return false
             * */

            // 点击哪个超链接，这里this就是谁
            // 点击链接后删除指定员工
            let tr = this.parentNode.parentNode

            // 获取要删除的员工的名字
            let name = tr.firstElementChild.innerHTML

            // confirm()用来弹出一个确认框
            // let isDel = confirm('确认删除吗？');

            if (confirm(`确认删除【${name}】吗？`)) {
              // 删除tr
              tr.parentNode.removeChild(tr)
            }

            // 取消默认行为
            return false
          }
        }
      }
    </script>
  </head>
  <body>
    <table id="employeeTable">
      <tr>
        <th>Name</th>
        <th>Email</th>
        <th>Salary</th>
        <th>&nbsp;</th>
      </tr>
      <tr>
        <td>Tom</td>
        <td>tom@tom.com</td>
        <td>5000</td>
        <td><a href="deleteEmp?id=001">Delete</a></td>
      </tr>
      <tr>
        <td>Jerry</td>
        <td>jerry@sohu.com</td>
        <td>8000</td>
        <td><a href="deleteEmp?id=002">Delete</a></td>
      </tr>
      <tr>
        <td>Bob</td>
        <td>bob@tom.com</td>
        <td>10000</td>
        <td><a href="deleteEmp?id=003">Delete</a></td>
      </tr>
    </table>

    <div id="formDiv">
      <h4>添加新员工</h4>

      <table>
        <tr>
          <td class="word">name:</td>
          <td class="inp">
            <input type="text" name="empName" id="empName" />
          </td>
        </tr>
        <tr>
          <td class="word">email:</td>
          <td class="inp">
            <input type="text" name="email" id="email" />
          </td>
        </tr>
        <tr>
          <td class="word">salary:</td>
          <td class="inp">
            <input type="text" name="salary" id="salary" />
          </td>
        </tr>
        <tr>
          <td colspan="2" align="center">
            <button id="addEmpButton">Submit</button>
          </td>
        </tr>
      </table>
    </div>
  </body>
</html>
```

## 114\_练习 2

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <title>添加删除记录练习</title>
    <style>
      #total {
        width: 450px;
        margin-left: auto;
        margin-right: auto;
      }

      ul {
        list-style-type: none;
      }

      li {
        border-style: solid;
        border-width: 1px;
        padding: 5px;
        margin: 5px;
        background-color: #99ff99;
        float: left;
      }

      .inner {
        width: 400px;
        border-style: solid;
        border-width: 1px;
        margin: 10px;
        padding: 10px;
        float: left;
      }

      #employeeTable {
        border-spacing: 1px;
        background-color: black;
        margin: 80px auto 10px auto;
      }

      th,
      td {
        background-color: white;
      }

      #formDiv {
        width: 250px;
        border-style: solid;
        border-width: 1px;
        margin: 50px auto 10px auto;
        padding: 10px;
      }

      #formDiv input {
        width: 100%;
      }

      .word {
        width: 40px;
      }

      .inp {
        width: 200px;
      }
    </style>

    <script>
      window.onload = function () {
        // 提取删除的函数
        function delA() {
          /*
           * 	点击超链接后，页面会发生跳转这是超链接的默认行为,
           * 		如果不希望默认行为的发生，可以在响应函数的最后
           * 		return false
           * */

          // 点击哪个超链接，这里this就是谁
          // 点击链接后删除指定员工
          let tr = this.parentNode.parentNode

          // 获取要删除的员工的名字
          let name = tr.firstElementChild.innerHTML

          // confirm()用来弹出一个确认框
          // let isDel = confirm('确认删除吗？');

          if (confirm(`确认删除【${name}】吗？`)) {
            // 删除tr
            tr.parentNode.removeChild(tr)
          }

          // 取消默认行为
          return false
        }

        /*
         * 点击超链接后，删除指定员工
         * */

        // 获取所有的超链接
        let links = document.getElementsByTagName('a')
        // 遍历超链接
        for (let i = 0; i < links.length; i++) {
          // 为超链接绑定单击响应函数
          links[i].onclick = delA
        }

        /*
			点击按钮后，将员工信息添加到表格中
			* */
        // 获取按钮对象
        let addEmpButton = document.getElementById('addEmpButton')
        addEmpButton.onclick = function () {
          // 获取员工的姓名
          let name = document.getElementById('empName').value
          // 邮件
          let email = document.getElementById('email').value
          // 薪水
          let salary = document.getElementById('salary').value

          // alert(name+"--"+email+'--'+salary);
          // 将员工信息添加到表格中
          /*
				*
				* 	<tr>
						<td>Tom</td>
						<td>tom@tom.com</td>
						<td>5000</td>
						<td><a href="deleteEmp?id=001">Delete</a></td>
					</tr>
				* */
          // 创建一个tr
          let tr = document.createElement('tr')

          // 创建4个td
          let nameTd = document.createElement('td')
          let emailTd = document.createElement('td')
          let salaryTd = document.createElement('td')
          let aTd = document.createElement('td')

          // 创建一个超链接
          let link = document.createElement('a')
          // 给超链接添加href属性
          link.href = 'javascript:;'
          // 单独为link绑定一个事件
          link.onclick = delA

          // 创建四个文本节点
          let nameTxt = document.createTextNode(name)
          let emailTxt = document.createTextNode(email)
          let salaryTxt = document.createTextNode(salary)
          let delTxt = document.createTextNode('Delete')

          // 将文本节点放入到元素中
          nameTd.appendChild(nameTxt)
          emailTd.appendChild(emailTxt)
          salaryTd.appendChild(salaryTxt)
          link.appendChild(delTxt)
          aTd.appendChild(link)

          // 将td放入到tr中
          tr.appendChild(nameTd)
          tr.appendChild(emailTd)
          tr.appendChild(salaryTd)
          tr.appendChild(aTd)

          // 获取table
          /*
           * 创建一个表格时，如果不指定thead tfoot tbody这些标签，
           * 	浏览器会自动创建一个tbody标签，然后将所有的tr都放入到tbody中
           * */
          let employeeTable = document.getElementById('employeeTable')
          // 获取tbody
          let tbody = employeeTable.getElementsByTagName('tbody')[0]
          tbody.appendChild(tr)
        }
      }
    </script>
  </head>
  <body>
    <table id="employeeTable">
      <tr>
        <th>Name</th>
        <th>Email</th>
        <th>Salary</th>
        <th>&nbsp;</th>
      </tr>
      <tr>
        <td>Tom</td>
        <td>tom@tom.com</td>
        <td>5000</td>
        <td><a href="deleteEmp?id=001">Delete</a></td>
      </tr>
      <tr>
        <td>Jerry</td>
        <td>jerry@sohu.com</td>
        <td>8000</td>
        <td><a href="deleteEmp?id=002">Delete</a></td>
      </tr>
      <tr>
        <td>Bob</td>
        <td>bob@tom.com</td>
        <td>10000</td>
        <td><a href="deleteEmp?id=003">Delete</a></td>
      </tr>
    </table>

    <div id="formDiv">
      <h4>添加新员工</h4>

      <table>
        <tr>
          <td class="word">name:</td>
          <td class="inp">
            <input type="text" name="empName" id="empName" />
          </td>
        </tr>
        <tr>
          <td class="word">email:</td>
          <td class="inp">
            <input type="text" name="email" id="email" />
          </td>
        </tr>
        <tr>
          <td class="word">salary:</td>
          <td class="inp">
            <input type="text" name="salary" id="salary" />
          </td>
        </tr>
        <tr>
          <td colspan="2" align="center">
            <button id="addEmpButton">Submit</button>
          </td>
        </tr>
      </table>
    </div>
  </body>
</html>
```

# day12

## 115\_复习

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <script>
      window.onload = function () {
        let allLi = document.getElementsByTagName('li')
        let allLi2 = document.querySelectorAll('li')

        document.getElementById('btn01').onclick = function () {
          let zzj = document.getElementById('zzj')
          let list1 = document.getElementById('list1')

          // cloneNode() 创建一个当前节点副本
          // cloneNode(true) 深复制
          let zzj2 = zzj.cloneNode(true)
          // 修改id
          zzj2.id = 'zzj2'
          list1.appendChild(zzj2)
          // console.log(zzj);
          // console.log(zzj2);
        }

        document.getElementById('btn02').onclick = function () {
          console.log(allLi) // HTMLCollection 可以实时的更新其中元素
          console.log(allLi2) // NodeList  不会实时更新，获取几个就是几个
        }
      }
    </script>
  </head>
  <body>
    <button id="btn01">按钮1</button>
    <button id="btn02">按钮2</button>

    <ul id="list1">
      <li id="swk">孙悟空</li>
      <li>猪八戒</li>
    </ul>

    <ul id="list2">
      <li>白骨精</li>
      <li id="zzj">蜘蛛精</li>
    </ul>
  </body>
</html>
```

## 116\_练习 2

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <title>添加删除记录练习</title>
    <style>
      #total {
        width: 450px;
        margin-left: auto;
        margin-right: auto;
      }

      ul {
        list-style-type: none;
      }

      li {
        border-style: solid;
        border-width: 1px;
        padding: 5px;
        margin: 5px;
        background-color: #99ff99;
        float: left;
      }

      .inner {
        width: 400px;
        border-style: solid;
        border-width: 1px;
        margin: 10px;
        padding: 10px;
        float: left;
      }

      #employeeTable {
        border-spacing: 1px;
        background-color: black;
        margin: 80px auto 10px auto;
      }

      th,
      td {
        background-color: white;
      }

      #formDiv {
        width: 250px;
        border-style: solid;
        border-width: 1px;
        margin: 50px auto 10px auto;
        padding: 10px;
      }

      #formDiv input {
        width: 100%;
      }

      .word {
        width: 40px;
      }

      .inp {
        width: 200px;
      }
    </style>

    <script>
      window.onload = function () {
        // 提取删除的函数
        function delA() {
          /*
           * 	点击超链接后，页面会发生跳转这是超链接的默认行为,
           * 		如果不希望默认行为的发生，可以在响应函数的最后
           * 		return false
           * */

          // 点击哪个超链接，这里this就是谁
          // 点击链接后删除指定员工
          let tr = this.parentNode.parentNode

          // 获取要删除的员工的名字
          let name = tr.firstElementChild.innerHTML

          // confirm()用来弹出一个确认框
          // let isDel = confirm('确认删除吗？');

          if (confirm(`确认删除【${name}】吗？`)) {
            // 删除tr
            tr.parentNode.removeChild(tr)
          }

          // 取消默认行为
          return false
        }

        /*
         * 点击超链接后，删除指定员工
         * */

        // 获取所有的超链接
        let links = document.getElementsByTagName('a')
        // 遍历超链接
        for (let i = 0; i < links.length; i++) {
          // 为超链接绑定单击响应函数
          links[i].onclick = delA
        }

        /*
			点击按钮后，将员工信息添加到表格中
			* */
        // 获取按钮对象
        let addEmpButton = document.getElementById('addEmpButton')
        addEmpButton.onclick = function () {
          // 获取员工的姓名
          let name = document.getElementById('empName').value
          // 邮件
          let email = document.getElementById('email').value
          // 薪水
          let salary = document.getElementById('salary').value

          // alert(name+"--"+email+'--'+salary);
          // 将员工信息添加到表格中
          /*
				*
				* 	<tr>
						<td>Tom</td>
						<td>tom@tom.com</td>
						<td>5000</td>
						<td><a href="deleteEmp?id=001">Delete</a></td>
					</tr>
				* */
          // 创建一个tr
          let tr = document.createElement('tr')
          // 设置tr内部的html代码
          // tr.innerHTML = `<td>${name}</td>
          // 				<td>${email}</td>
          // 				<td>${salary}</td>
          // 				<td><a href="javascript:;">Delete</a></td>`

          tr.innerHTML =
            '<td>' +
            name +
            '</td>' +
            '<td>' +
            email +
            '</td>' +
            '<td>' +
            salary +
            '</td>' +
            '<td><a href="javascript:;">Delete</a></td>'

          // 获取tr中的a
          let link = tr.getElementsByTagName('a')[0]
          link.onclick = delA

          // 获取table
          /*
           * 创建一个表格时，如果不指定thead tfoot tbody这些标签，
           * 	浏览器会自动创建一个tbody标签，然后将所有的tr都放入到tbody中
           * */
          let employeeTable = document.getElementById('employeeTable')
          // 获取tbody
          let tbody = employeeTable.getElementsByTagName('tbody')[0]

          // tbody.innerHTML += '<tr></tr>';
          // tbody.insertAdjacentHTML('beforeend', '<tr></tr>')
          tbody.appendChild(tr)
        }
      }
    </script>
  </head>
  <body>
    <table id="employeeTable">
      <tr>
        <th>Name</th>
        <th>Email</th>
        <th>Salary</th>
        <th>&nbsp;</th>
      </tr>
      <tr>
        <td>Tom</td>
        <td>tom@tom.com</td>
        <td>5000</td>
        <td><a href="deleteEmp?id=001">Delete</a></td>
      </tr>
      <tr>
        <td>Jerry</td>
        <td>jerry@sohu.com</td>
        <td>8000</td>
        <td><a href="deleteEmp?id=002">Delete</a></td>
      </tr>
      <tr>
        <td>Bob</td>
        <td>bob@tom.com</td>
        <td>10000</td>
        <td><a href="deleteEmp?id=003">Delete</a></td>
      </tr>
    </table>

    <div id="formDiv">
      <h4>添加新员工</h4>

      <table>
        <tr>
          <td class="word">name:</td>
          <td class="inp">
            <input type="text" name="empName" id="empName" />
          </td>
        </tr>
        <tr>
          <td class="word">email:</td>
          <td class="inp">
            <input type="text" name="email" id="email" />
          </td>
        </tr>
        <tr>
          <td class="word">salary:</td>
          <td class="inp">
            <input type="text" name="salary" id="salary" />
          </td>
        </tr>
        <tr>
          <td colspan="2" align="center">
            <button id="addEmpButton">Submit</button>
          </td>
        </tr>
      </table>
    </div>
  </body>
</html>
```

## 117\_操作样式

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <style>
      #box1 {
        width: 100px;
        height: 100px;
        background-color: tomato;
        margin-top: 20px;
      }
    </style>
  </head>
  <body>
    <button id="btn01">按钮1</button>
    <button id="btn02">按钮2</button>

    <div id="box1"></div>

    <script>
      // 获取box1
      let box1 = document.getElementById('box1')
      // 创建一个变量
      let width = 100

      document.getElementById('btn01').onclick = function () {
        /*
         *   修改元素的样式：
         *       元素.style.样式名 = 样式值
         *         - 样式名通常可以直接写
         *               但是如果样式名中带有-必须进行修改
         *               将-号去掉，-后的字母大写
         *           background-color --> backgroundColor
         *           border-left-width --> borderLeftWidth
         *
         *       - 通过style所修改的样式都是内联样式，所有修改完成后通常会立即生效
         * */
        // 获取元素当前宽度
        let currentWidth = getComputedStyle(box1).width
        // 点击按钮修改box1的大小
        box1.style.width = parseInt(currentWidth) + 10 + 'px'
        box1.style.height = parseInt(currentWidth) + 10 + 'px'
        box1.style.backgroundColor = 'orange'
      }

      document.getElementById('btn02').onclick = function () {
        // 读取元素的样式 通过style读取样式时，只能读取内联样式
        // alert(box1.style.width);

        /*
            getComputedStyle()
                - 该函数用来获取元素的当前样式
                - 参数：
                    1.要获取样式的对象
                    2.要获取的样式伪元素

                - 返回值：
                    返回一个对象，对象中存储了当前元素的所有样式
        */

        let box1Style = getComputedStyle(box1)

        // console.log(box1Style);
        // alert(box1Style.backgroundColor);
        alert(box1Style.width)
      }
    </script>
  </body>
</html>
```

## 118\_获取样式的其他方式

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <style>
      #box1 {
        width: 100px;
        height: 100px;
        background-color: tomato;
        margin-top: 20px;

        padding: 10px;
        border: 10px skyblue solid;

        overflow: auto;
      }

      #box2 {
        width: 600px;
        height: 600px;
        background-color: yellow;
      }
    </style>
  </head>
  <body>
    <button id="btn01">按钮1</button>
    <button id="btn02">按钮2</button>
    <div style="width: 300px;height: 300px;background-color: #bfa;">
      <div id="box1">
        <div id="box2"></div>
      </div>
    </div>

    <script>
      // 获取box1
      let box1 = document.getElementById('box1')

      document.getElementById('btn01').onclick = function () {
        /*
         *   clientWidth，clientHeight 用来获取盒子内部大小（包含内边距和内容区）
         *   offsetWidth，offsetHeight 用来获取盒子可见框的大小（内容区、内边距和边框）
         * */
        // alert(box1.offsetWidth);
        // box1.offsetWidth = 300;

        /*
         *   offsetParent 获取当前元素的定位父元素
         *       - 定位父元素是离当前元素最近的开启了定位的祖先元素，
         *           如果所有的祖先元素都没有开启定位，则返回body
         *
         *   offsetLeft 获取当前元素相对于其定位元素（offsetParent）的左侧偏移量
         *   offsetTop  获取当前元素相对于其定位元素（offsetParent）的上偏移量
         * */

        // console.log(box1.offsetParent);

        console.log(box1.offsetLeft)
      }

      document.getElementById('btn02').onclick = function () {
        /*
         * scrollHeight
         * scrollWidth
         *   - 用来获取元素的滚动区域大小
         * */
        /*console.log(box1.scrollHeight);
        console.log(box1.scrollWidth);*/

        /*
         *   scrollTop 垂直滚动条的滚动的距离
         *   scrollLeft 水平滚动条滚动的距离
         *       当 scrollHeight - scrollTop === clientHeight 说明垂直滚动条到底了
         *       当 scrollWidth - scrollLeft === clientWidth 说明水平滚动条到底了
         *
         * */
        console.log(box1.scrollHeight - box1.scrollTop)
        console.log(box1.clientHeight)
      }
    </script>
  </body>
</html>
```

## 119\_练习

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <style>
      #info {
        width: 400px;
        height: 200px;
        overflow: auto;
        background-color: #bfa;
      }
    </style>
  </head>
  <body>
    <h2>欢迎注册，请仔细阅读以下协议：</h2>
    <p id="info">
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
      亲爱的用户，请一定要遵守我们的协议，要不然就别注册
    </p>

    <input disabled type="checkbox" /> 我已仔细阅读，并严重同意以上协议
    <input disabled type="submit" value="注册" />

    <script>
      /*
       *   当协议的滚动条到底时，使两个input变得可用
       * */
      // 获取id为info的p元素
      let info = document.getElementById('info')
      // 获取两个input
      let inp = document.getElementsByTagName('input')
      //onscroll 会在元素的滚动条滚动的时候触发
      info.onscroll = function () {
        // 检查垂直滚动条是否到底
        if (Math.floor(info.scrollHeight - info.scrollTop) === info.clientHeight) {
          // 进入判断说明滚动条已经滚动到底，使两个input可用
          // disabled 属性可以用来设置元素是否可用，它需要一个布尔值，如果是true，则表示不可用
          //   如果是false则表示可用
          inp[0].disabled = false
          inp[1].disabled = false
        }
      }
    </script>
  </body>
</html>
```

## 120\_事件对象

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
  <head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
    <title>Insert title here</title>
    <style type="text/css">
      #areaDiv {
        border: 1px solid black;
        width: 300px;
        height: 50px;
        margin-bottom: 10px;
      }

      #showMsg {
        border: 1px solid black;
        width: 300px;
        height: 20px;
      }
    </style>
  </head>
  <body>
    <div id="areaDiv"></div>
    <div id="showMsg"></div>

    <script>
      /*
       * 	当鼠标在大div（areaDiv）中移动时，在小div（showMsg）中显示鼠标的坐标
       * */
      let areaDiv = document.getElementById('areaDiv')
      let showMsg = document.getElementById('showMsg')

      /*
       * 	当事件的响应函数触发时，浏览器都会传递一个对象作为回调函数的实参，
       * 		这个实参就是事件对象，事件对象中存储了所有当前事件相关的信息，
       * 		比如：事件是谁触发、触发时哪个按键被按下、触发时鼠标的坐标...
       * */

      // 为areaDiv绑定一个鼠标移动的事件
      areaDiv.onmousemove = function (event) {
        // 获取鼠标的x轴和y轴
        let x = event.clientX
        let y = event.clientY

        // 在showMsg显示坐标
        showMsg.innerHTML = 'x = ' + x + ' , y = ' + y
      }
    </script>
  </body>
</html>
```

## 121\_练习

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <style>
      body {
        height: 3000px;
      }
      #box1 {
        width: 100px;
        height: 100px;
        background-color: tomato;
        /*position: fixed;*/
        position: absolute;
      }
    </style>
  </head>
  <body>
    <div id="box1"></div>

    <script>
      /*
        使 div 可以根据鼠标移动
    * */
      // 获取box1
      let box1 = document.getElementById('box1')
      // 为document绑定一个鼠标移动的事件
      document.onmousemove = function (event) {
        // 获取垂直滚动条滚动的距离
        // console.log(document.documentElement.scrollTop);

        // 获取鼠标指针的坐标
        let x = event.clientX
        let y = event.clientY

        // pageX 和 pageY 可以用来获取鼠标相对于整个页面的坐标
        // let x = event.pageX;
        // let y = event.pageY;
        // 将鼠标的坐标设置为box1的偏移量
        box1.style.left = x + document.documentElement.scrollLeft + 'px'
        box1.style.top = y + document.documentElement.scrollTop + 'px'
      }
    </script>
  </body>
</html>
```

## 122\_冒泡

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <style>
      #box1 {
        width: 100px;
        height: 100px;
        background-color: tomato;
      }

      #s1 {
        background-color: yellow;
        position: absolute;
        left: 200px;
        top: 500px;
      }
    </style>
  </head>
  <body>
    <div id="box1">
      我是div
      <span id="s1">我是span</span>
    </div>

    <script>
      /*
       *   冒泡（bubble）
       *       - 冒泡指的是事件的向上传导，当元素上的某个事件被触发时，
       *           其祖先元素上的相同事件也会同时被触发
       *       - 冒泡的存在在大部分情况都是有利的，简化我们的开发
       *       - 冒泡的发生只和结构有关，和元素的位置无关
       *       - 要取消事件的冒泡需要用到事件对象
       *           只需将事件对象的 cancelBubble 属性设置true，即可取消冒泡
       *           也可以通过 事件的对象 stopPropagation() 方法来停止冒泡
       * */
      // 分别为body box1 和 s1绑定单击响应函数
      let s1 = document.getElementById('s1')
      s1.onclick = function (event) {
        // event.cancelBubble = true;
        // 停止事件的冒泡
        // event.stopPropagation();
        alert('我是s1上的单击响应函数！')
      }

      let box1 = document.getElementById('box1')
      box1.onclick = function (event) {
        event.stopPropagation()
        alert('我是box1上的单击响应函数!')
      }

      document.body.onclick = function () {
        alert('我是body上的单击响应函数!')
      }
    </script>
  </body>
</html>
```

## 123\_练习

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <style>
      body {
        height: 3000px;
      }
      #box1 {
        width: 100px;
        height: 100px;
        background-color: tomato;
        /*position: fixed;*/
        position: absolute;
      }

      #box2 {
        width: 400px;
        height: 400px;
        background-color: #bfa;
      }
    </style>
  </head>
  <body>
    <div id="box1"></div>
    <div id="box2"></div>

    <script>
      /*
        使 div 可以根据鼠标移动
    * */
      // 获取box1
      let box1 = document.getElementById('box1')
      // 为document绑定一个鼠标移动的事件
      document.onmousemove = function (event) {
        // 获取垂直滚动条滚动的距离
        // console.log(document.documentElement.scrollTop);

        // 获取鼠标指针的坐标
        let x = event.clientX
        let y = event.clientY

        // pageX 和 pageY 可以用来获取鼠标相对于整个页面的坐标
        // let x = event.pageX;
        // let y = event.pageY;
        // 将鼠标的坐标设置为box1的偏移量
        box1.style.left = x + document.documentElement.scrollLeft + 'px'
        box1.style.top = y + document.documentElement.scrollTop + 'px'
      }

      // let box2 = document.getElementById('box2');
      // box2.onmousemove = function (event) {
      //     event.stopPropagation();
      // };
      //
      // box1.onmousemove = function (event) {
      //     event.stopPropagation();
      // };
    </script>
  </body>
</html>
```

## 124\_事件的绑定

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
  </head>
  <body>
    <button id="btn01">按钮1</button>

    <script>
      /*
       *   使用 属性 来绑定事件时，一个元素上同时只能为一个事件绑定一个响应函数
       *       如果同时为一个事件设置了多个响应函数，则后边的会覆盖掉前边
       * */

      let btn01 = document.getElementById('btn01')
      // btn01.onclick = function () {
      //     alert(1);
      // };
      //
      /*btn01.onclick = function () {
        alert(2);
    };

    btn01.onclick = null;*/

      /*
       *   可以通过 addEventListener() 来为元素设置响应函数
       *       参数：
       *           1.要绑定的事件，需要一个事件的字符串作为参数（不要on）
       *           2.事件的回调函数
       *           3.是否在捕获阶段触发事件，需要一个布尔值
       *               true 会发生事件的捕获
       *               false 不会（默认值）
       *
       *   通过该方式所绑定的事件不会互相干扰，可以为同一个事件绑定多个响应函数
       *       事件触发时，函数会按照绑定的顺序执行
       *
       *  removeEventListener()可以用来移除一个事件的响应函数
       *   - 移除时的参数必须和设置时的一模一样
       * */

      function clickHandler(event) {
        alert(1)
      }
      btn01.addEventListener('click', clickHandler)

      btn01.removeEventListener('click', clickHandler)

      //
      // btn01.addEventListener('click', function (event) {
      //     alert(2);
      // });
      //
      // btn01.addEventListener('click', function (event) {
      //     alert(3);
      // });
    </script>
  </body>
</html>
```

## 125\_事件的传播

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <style>
      #box1 {
        width: 400px;
        height: 400px;
        background-color: skyblue;
      }

      #box2 {
        width: 300px;
        height: 300px;
        background-color: #bfa;
      }

      #box3 {
        width: 200px;
        height: 200px;
        background-color: yellow;
      }
    </style>
  </head>
  <body>
    <div id="box1">
      <div id="box2">
        <div id="box3"></div>
      </div>
    </div>

    <script>
      /*
       *   关于事件的传播微软公司和网景公司有着不同的理解：
       *       微软认为，事件应该是由内向外传播，
       *           也就是先触发后代元素上的事件，在触发祖先元素的事件（事件的冒泡）
       *       网景认为，事件应该是由外向内传播
       *           先触发祖先元素的上的事件，在触发后代元素的事件（事件的捕获）
       *       W3C将两种理念进行整合，将事件分为了三个阶段：
       *           1.事件的捕获
       *               - 从最外层元素（window）向目标元素进行事件的捕获
       *           2.目标元素
       *               - 事件捕获到目标元素，捕获停止
       *           3.事件的冒泡
       *               - 从目标元素开始，向外层元素进行事件的冒泡
       *       - 默认情况下，事件是在冒泡阶段触发的
       * */

      let box1 = document.getElementById('box1')
      let box2 = document.getElementById('box2')
      let box3 = document.getElementById('box3')

      box1.addEventListener(
        'click',
        function () {
          alert(1)
        },
        true
      )

      box2.addEventListener(
        'click',
        function () {
          alert(2)
        },
        true
      )

      box3.addEventListener(
        'click',
        function () {
          alert(3)
        },
        true
      )
    </script>
  </body>
</html>
```

# day13

## 126\_复习

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <style>
      #box1 {
        width: 100px;
        height: 100px;
        background-color: tomato;
      }
    </style>
  </head>
  <body>
    <div id="box1"></div>

    <a id="baidu" href="https://www.baidu.com">去Baidu</a>

    <script>
      let box1 = document.getElementById('box1')
      // console.log(getComputedStyle(box1).backgroundColor);

      // box1.onclick = function (event) {
      //     alert(event);
      // };

      box1.addEventListener('click', function (event) {
        alert(event)
        event.stopPropagation()
      })

      let baidu = document.getElementById('baidu')
      baidu.addEventListener('click', function (event) {
        // 取消默认行为
        event.preventDefault()
        alert(123)
      })

      // baidu.onclick = function (event) {
      //     event.preventDefault();
      //     alert(123);
      // };
    </script>
  </body>
</html>
```

## 127\_事件的委派

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
  </head>
  <body>
    <button id="btn01">点我一下</button>

    <ul>
      <li>
        <a href="javascript:;">超链接一</a>
      </li>
      <li>
        <a href="javascript:;">超链接二</a>
      </li>
      <li>
        <a href="javascript:;">超链接三</a>
      </li>
    </ul>

    <script>
      /*
       * 目前的问题：
       *   1.目前事件绑定的代码编写在了for循环中，for循环执行几次就绑定了几个事件，
       *       同时产生了几个回调函数，但是回调函数的功能是一样的，这样做比较浪费内存
       *   2.当前的事件只会绑定给已有的元素，对于新曾的元素来说，必须重新绑定事件
       *
       * 我们的希望：
       *   仅仅只绑定一次事件，就可以让所有的（包括新增的元素）都具有该事件！
       *
       * 事件的委派（事件的委托）：
       *   - 当需要为多个元素绑定相同的响应函数时，可以统一将事件绑定给它们共同的祖先元素，
       *       这样只需要绑定一次即可让所有的元素都具有该事件，即使元素是新增的也会具有该事件。
       *
       *
       *
       * */
      // 获取所有的超链接
      let links = document.getElementsByTagName('a')

      // 获取ul
      let ul = document.getElementsByTagName('ul')[0]

      // 将事件绑定给ul
      ul.addEventListener('click', function (event) {
        // 判断触发事件的对象是否是超链接
        // 在事件的响应函数中，this表示的是事件绑定的对象
        // alert(this);

        // 在事件对象中有一个属性叫做target，它表示的是触发事件的对象

        // alert(event.target.tagName);

        // 判断事件是否由超链接触发
        if (event.target.tagName.toUpperCase() === 'A') {
          event.preventDefault()
          alert('我是ul上的单击事件！')
        }
      })

      // 点击按钮后，添加li
      let btn01 = document.getElementById('btn01')
      btn01.addEventListener('click', function () {
        // 向ul中添加li
        /*
        * <li>
                <a href="javascript:;">超链接三</a>
            </li>
        * */
        ul.insertAdjacentHTML('beforeend', '<li><a href="javascript:;">新超链接</a></li>')
      })
    </script>
  </body>
</html>
```

## 128\_拖拽

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Title</title>
    <style>
      #box1 {
        width: 100px;
        height: 100px;
        background-color: tomato;
        position: absolute;
      }
    </style>
  </head>
  <body>
    <div id="box1"></div>

    <div
      style="width: 100px;height: 100px;background-color: orange; position:absolute; top: 100px;left: 400px;"
    ></div>

    <script>
      /*
       *   通过鼠标，拖拽box1移动
       *       1.当鼠标在box1上按下时，功能开始  （mousedown）
       *       2.鼠标移动，box1跟随鼠标一起移动  （mousemove）
       *       3.鼠标松开，功能结束，           （mouseup）
       *           box1固定在当前位置不在跟随鼠标移动
       * */

      // 获取id为box1的元素
      let box1 = document.getElementById('box1')
      // 为box1绑定一个鼠标按下的事件
      box1.onmousedown = function (event) {
        /*
         *   问题：如何保持鼠标指针和被拖拽的元素相对位置不变
         * */

        // 计算水平方向的偏移
        let left = event.clientX - box1.offsetLeft
        // 计算垂直方向的偏移
        let top = event.clientY - box1.offsetTop

        // 当鼠标在box1上按下时，功能开始
        // 为document来绑定一个鼠标移动事件，使元素可以跟随鼠标移动
        document.onmousemove = function (event) {
          box1.style.left = event.clientX - left + 'px'
          box1.style.top = event.clientY - top + 'px'
        }
        // 鼠标松开功能结束 mouseup
        document.onmouseup = function () {
          // 取消鼠标移动的事件
          document.onmousemove = null
          // 取消鼠标松开的事件
          document.onmouseup = null
        }
      }
    </script>
  </body>
</html>
```

javascript 原型链机制：

![image-20230320101442777](D:\研究生\大数据技术结课作业\图片\image-20230320101442777.png)

如图：

function B.protoType.constructor=function.B。

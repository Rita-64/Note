## JavaScript 学习笔记1

---

### <1> 书写位置

##### 内部形式

JavaScript程序不可以独立运行，需要**嵌入到HTML中**，通过浏览器来运行JavaScript的代码，在HTML中通过**<script>**标签引入到HTML中

例如：

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <title>第一个 JS</title>
</head>
<body>

  <script>

        let uname = prompt('请输入文本')
        document.write(uname)
  </script>

</body>
</html>
```


这里的Javascript代码**被覆盖在<script>和</script>之间**

##### 外部形式

可以通过**外部引入**的方式来引入Javascript代码，将JavaScript代码写在独立的以.js为结尾的文件内，然后再通过script标签来引入

例如：
```js
// demo.js
document.write('你好，又见面了，还是说，这是第一次？')

```

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <title>第一个 JS</title>
</head>
<body>

  <script src = "demo.js">
  </script>

</body>
</html>

```

> 注：如果script标签使用src属性引入某.js文件，标签代码会被**忽略**

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <title>第一个 JS</title>
</head>
<body>

  <script src = "demo.js">
    document.write('sha dou mei you')// 这里的代码会被忽略
  </script>

</body>
</html>

```

---

### <2> 注释与结束符

##### 注释

通过注释可以**添加备注信息**或者**令一段代码被屏蔽**

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <title>Document</title>
</head>
<body>

// 单行注释 一次可以注释一行
// 可以多次进行注释

/*
    这里是多行注释
    在这片区域可以任意换行
    多少行都行
*/
  <script>

        let uname = prompt('请输入文本')
        document.write(uname)
    // document.write('Error')  
    //  这里不会输出Error，因为被注释了
  </script>

</body>
</html>
```

##### 结束符

在JavaScript里，';'可以表示一段代码的结束（同C++），但是与C++不同的是这里的';'多数情况下可以省略，用回车（enter）替代即可

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <title>Document</title>
</head>
<body>

  <script>
    alert(1);
    alert(2)
    // 这里1和2都可以在提示弹窗里显示出来，说明两种形式
  </script>

</body>
</html>
```

这里需要统一一下，最好一篇代码里只出现';'或只不出现';'，很多人主张不加';'

---

### <3> 输入与输出

输出和输入也可理解为**人和计算机的交互**，用户通过键盘、鼠标等向计算机输入信息，计算机处理后再展示结果给用户，这便是一次输入和输出的过程。

> **输入：prompt()** 输入任意内容以弹窗形式出现在浏览器上，提示用户输入内容

> **输出：
    （1）alert()** 以弹窗形式展示输出内容，一般起提示作用
    **（2）document.write()** 在浏览器的界面中输出内容
    **（3）console.log()** 在日志中输出内容，通常是给程序员看的


```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Document</title>
</head>
<body>
  
  <script> 
    document.write('document')
    alert('ALERT!');
    console.log('console')
    prompt('请输入文本')
  </script>
</body>
</html>
```
> 注：这里会先执行`alert()`和`prompt()`，后执行`document.write()`和`console.log()`

---

### <4> 变量与声明

##### 变量

变量是计算机中用来**存储数据的“容器”**，它可以让计算机变得有记忆，通俗的理解变量就是使用**某个符号**来代表**某个具体的数值**

```js
x = 5 // 这里x代表数字5

y = 'Rita' // 这里y表示字符串Rita

num = prompt('请输入一些内容')

document.write(num) // 输出num里的内容
document.write('<br>') // 换行
document.write('num') // 注意，这里是输出‘num’而不是num的内容

```

##### 声明

声明（定义）变量部分有两种：**声明关键字，变量名（标识）**

> 结构：`let` + 变量名（变量名注意规范,后文提及了）

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Document</title>
</head>
<body>
  
  <script> 
    let age // let是关键字，age是变量名称
  </script>
</body>
</html>

```

> 注：**`let`和`var`**都是JavaScript声明变量的关键字，不推荐使用`var`。`var`在同一作用域下可以重复声明，比如说一个变量名i可以被重复定义多次，而取值以最后一次为准，不符合现代JavaScript的逻辑，所以不推荐使用`var`（C++也一样）

##### 赋值

声明（定义）变量相当于**创造了一个空的“容器”**，通过赋值向这个容器中**添加数据**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Document</title>
</head>
<body>
   <script> 
    let age // 声明变量age
    age = 18 // 赋值18
    document.write(age)

    // 也可以声明和赋值同时进行
    let str = 'hello world!'
    alert(str);
  </script>
</body>
</html>

```

##### 关键字`let`

以下是使用`let`时的注意事项：

1. 允许声明和赋值同时进行
2. 不允许重复声明
3. 允许同时声明多个变量并赋值
4. JavaScript中内置的一些关键字不能被当做变量名

##### 变量名命名规则

关于变量的名称（标识符）有一系列的规则需要遵守：

1. 只能是字母、数字、下划线、$，且不能能数字开头
2. 字母区分大小写，如 Age 和 age 是不同的变量
3. JavaScript 内部已占用于单词（关键字或保留字）不允许使用
4. 尽量保证变量具有一定的语义，见字知义

> 注：所谓关键字是指 JavaScript 内部使用的词语，如`let`和`var`，保留字是指 JavaScript 内部目前没有使用的词语，但是将来可能会使用词语。

##### 常量

使用**const**声明的变量是常量

当某种变量永远不会改变时，可以用`const`来声明而非`let`

```js

const PI = 3.14
const g = 9.8

```

> 注意: 常量不允许重新赋值,声明的时候必须赋值（初始化）

---

### <5> 数据类型

计算机程序可以处理大量的数据，为了方便数据的管理，将数据分成了不同的类型：

> 这里可以使用`typeof`来检测数据类型

##### （1）数值类型 

即数字，可以是正数，负数，整数，小数

```js

    let score = 100 // 正整数
    let price = 12.345 // 小数
    let temperature = -40 // 负数

    document.write(typeof score) // 结果为 number
    document.write(typeof price) // 结果为 number
    document.write(typeof temperature) // 结果为 number

```

##### (2) 字符串类型

通过单引号（''） 、双引号（""）或反引号包裹的数据都叫字符串，单引号和双引号没有本质上的区别，**推荐使用单引号**

> 注:
1. 无论单引号或是双引号必须成对使用
2. 单引号/双引号可以互相嵌套，但是不以自已嵌套自已
3. 必要时可以使用转义符 \，输出单引号或双引号

```js

    let user_name = '小明' // 使用单引号
    let gender = "男" // 使用双引号
    let str = '123' // 看上去是数字，但是用引号包裹了就成了字符串了
    let str1 = '' // 这种情况叫空字符串
		
    documeent.write(typeof user_name) // 结果为 string
    documeent.write(typeof gender) // 结果为 string
    documeent.write(typeof str) // 结果为 string

```

##### (3) 布尔类型

表示肯定或否定时在计算机中对应的是布尔类型数据，它有**两个固定的值`true`和`false`**，表示肯定的数据用`true`，表示否定的数据用`false`。

```js

    let ok = true 
    ok = false 

    document.write(typeof isCool) // 结果为 boolean
```

##### (4) underfined

未定义是比较特殊的类型，**只有一个值undefined**，只声明变量，不赋值的情况下，**变量的默认值为undefined**，一般很少直接为某个变量赋值为undefined。

```js

    let tmp;
    document.write(typeof tmp) // 结果为 undefined

```

> 注：JavaScript 中变量的值决定了变量的数据类型，属于弱类型语言，与C++,Java相反。

##### sp. 类型转换

（1）隐式转换

某些运算符被执行时，系统内部**自动将数据类型进行转换**，这种转换称为隐式转换。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Document</title>
</head>
<body>
  <script> 
    let num = 13 // 数值
    let num2 = '2' // 字符串

    // 结果为 132
    // 原因是将数值 num 转换成了字符串，相当于 '13'
    // 然后 + 将两个字符串拼接到了一起
    console.log(num + num2)

    // 结果为 11
    // 原因是将字符串 num2 转换成了数值，相当于 2
    // 然后数值 13 减去 数值 2
    console.log(num - num2)

    let a = prompt('请输入一个数字')
    let b = prompt('请再输入一个数字')

    alert(a + b);
  </script>
</body>
</html>
```

> 注：'+'在隐式转换中具有特殊地位，当数值'+'字符串时会将整体变为字符串，还有一种情况，如果变量`a`是一个数字字符串，那么`+a`会把它转成数字，`+prompt()`同理

（2）显示转换

编写程序时过度依靠系统内部的隐式转换是不严禁的，因为隐式转换规律并不清晰，大多是靠经验总结的规律。为了避免因隐式转换带来的问题，通常根逻辑需要对数据进行显示转换。

通过`Number`显示转换成数值类型，当转换失败时结果为`NaN`（Not a Number）即不是一个数字。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Document</title>
</head>
<body>
  <script>
    let t = '12'
    let f = 8

    // 显式将字符串 12 转换成数值 12
    t = Number(t)

    // 检测转换后的类型
    // console.log(typeof t);
    console.log(t + f) // 结果为 20

    // 并不是所有的值都可以被转成数值类型
    let str = 'hello'
    // 将 hello 转成数值是不现实的，当无法转换成数值时，得到的结果为 NaN （Not a Number）
    console.log(Number(str))
  </script>
</body>
</html>
```

> 注：本文可能出现小问题，如果发现会及时改正的XD

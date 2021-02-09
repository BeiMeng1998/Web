# HTML

## HTML和XHTML有什么区别

HTML(HyperText Markup Language)超文本标记语言

XHTML(Extensible HyperText Markup Language)可扩展超文本标记语言

XHTML的表现方式与HTML类似，但比HTML更加严格

1.XHTML元素必须被正确嵌套

2.XHTML元素必须被关闭

3.XHTML标签名必须小写

4.XHTML必须有根元素


## !DOCTYPE文档声明的作用

H5不再是SGML的子集，所以H5不需要对DTD进行引用

H5的文档声明，声明当前网页是按照HTML5标准编写的

编写网页时一定要将H5的文档声明写在网页最上边

如果不写文档声明，有些浏览器会进入兼容模式

标准模式下网页的编排和JS运作模式都是以该浏览器支持的最高标准运行

而在兼容模式下，页面则以宽松向后兼容的方式显示，模拟老式浏览器的行为以防止站点无法工作

比如：若不声明DOCTYPE类型，IE6浏览器会将盒子模型解释为IE盒子模型，FireFox等会将其解释为W3C盒子模型

所以，为了页面的正常显示，一定要写文档声明

## 行内元素

a img input span textarea em strong i small cite q sup sub...

## 块元素

div p h1 ul ol li form table...

## 空元素

br hr link script

## attribute与property

attribute：HTML标签的预定义和自定义属性，设置的属性值只能为字符串

property：JS对象的直接属性

二者的同步关系：

1.property为非布尔值属性时，二者是实时同步的

2.property为布尔值属性时，attribute只会在第一次设置时影响property，之后二者不再同步

所以操作布尔值属性最好用property，非布尔值属性用attribute

## HTML自定义属性

date-xxx

`<div id='test' data-name-a-b-ccc='北梦夏栀'> </div>`

JS可通过元素的dataset属性对象以 驼峰命名 来访问

`console.log(test.dataset.nameABCcc)`

## meta标签

meta常用于定义页面的说明，字符集，关键字、简介和其它的元数据。这些元数据将服务于浏览器（如何布局或重载页面），搜索引擎和其它网络服务。

设置网页字符集
`<meta charset="UTF-8" />`

设置网页关键字
`<meta name="keywords" content="网页的关键字" />`

设置网页的描述
`<meta name="description" content="网页的描述" />`

设置viewport移动端视口
`<meta name="viewport" content="width=device-width, initial-scale=1">`

搜索引擎在检索页面时会检索页面中的关键字和描述

## img的title和alt有什么区别

title：当鼠标移动到元素上显示

alt：img的特有属性，当图片无法成功加载时，页面会显示alt属性值，并且搜索引擎会对有alt属性的图片进行收录


## HTML5新特性

1.绘画 canvas

2.用于媒介回放的 video 和 audio 元素

3.本地存储localstorage,sessionstorage

4.语义化标签，比如article、footer、header、nav、section

5.新增表单属性type placeholder autofocus required pattern

## HTML5语义化标签

常用的语义化标签hgroup header nav section footer article aside main

### hgroup

可以将多个h1~h6元素放在其中，比如文章的主标题和副标题结合

注意：连续多个h标签才用hgroup

### header

代表网页或者section的页眉，通常包含h标签或者hgroup

### nav

用于定义页面主要导航部分

### section

section元素代表文档中的节或段，段可以是一篇文章里按照主题的分段，节可以是指一个页面里的分组

注意：section不是一般意义上的容器元素，如果想作为样式展示和脚本的便利，可以用div

article，nav，aside可以理解为特殊的section，可以用article，nav，aside就不要用section

### article

article元素最容易跟section和div混淆，其实article代表一个在文档，页面或者网站中自成一体的独立内容

### aside

aside元素包含在article元素中作为主要内容的附属信息部分，其中的内容可以是与当前文章有关的相关资料，标签，名词解释等

在article元素之外使用作为页面或站点全局的附属信息部分，最典型的是侧边栏，其中的内容可以是日志串连，其他组的导航

## HTML5删除的标签

big，center，font, s...

frame，frameset，noframes

## shadow dom是什么

shadow dom是浏览器渲染dom树时，插入的一个并不在主dom树上的dom元素子树

在开发者工具的设置中开启 show user agent shadow DOM就可以看到shadow dom的结构

影子树是对一些技术实现的封装，比如以video为寄生宿主的影子树构建了播放器

这也就是为什么我们只加一个video标签就能够看到整个播放器的原因

我们可以对影子树进行操作，修改其样式等

## SVG和Canvas的区别

SVG和Canvas都是2D作图

SVG是矢量图，不受分辨率影响，缩小放大不失真

Canvas是位图，逐像素渲染，受分辨率影响，放大会失真

# CSS相关

## 两种盒模型

IE盒模型和W3C标准盒模型

IE盒模型的width和height是border-box

W3C标准盒模型的width和height是content-box

box-sizing: border-box; 将W3C盒模型转为IE盒模型

## 列举几个css中可继承和不可继承的属性

可继承：font, font-size, font-family, font-weight, font-style, text-indent, text-align, line-hight, word-spacing, color, visibility

不可继承：display, width, height, margin, padding, border, background, position, float, top, left, bottom, right

## 伪类和伪元素的区别

伪类主要是为了选中元素的某种特殊状态，伪类用单冒号

伪元素主要是为了创建DOM树以外的元素，伪元素用双冒号

## CSS filter

元素的滤镜或者说是元素的可视效果，如模糊程度，饱和度，透明度等等

## CSS选择器

ID选择器

类选择器 伪类选择器 属性选择器

元素选择器 伪元素选择器

通配选择器

子元素选择器 兄弟选择器 后代选择器

交集选择器 并集选择器

## CSS选择器优先级

### 1.首先按来源排序

CSS来源分三种：开发人员 用户(Internet选项-辅助功能-用户样式表）用户代理

权重由高到低依次是：

用户的重要声明

开发人员的重要声明

开发人员的正常声明

用户的正常声明

用户代理的声明

### 2.按选择器的特殊性排序

1.内联声明/行内声明特殊性 1 0 0 0

2.ID选择器特殊性 0 1 0 0

3.类，属性和伪类选择器特殊性 0 0 1 0

4.元素和伪元素选择器特殊性 0 0 0 1

5.通配选择器特殊性 0 0 0 0

6.继承没有特殊性

7.结合符对选择器特殊性没有一点贡献

当使用多个选择器与同一元素匹配时，不进位地计算其特殊性值，特殊性越大权重越高

重要声明也就是 !important 并没有特殊的特殊性值

浏览器会将正常声明和重要声明分为两组，两组内的声明冲突会在其内部解决

而当一个正常声明和重要声明冲突时，胜出的总是重要声明

### 3.顺序排序

如果选择器特殊性相同则按照顺序排序，新声明覆盖旧声明

## BFC(Block formatting context)

块级格式化上下文，它是一个独立的渲染区域，只有Block-level box参与，它规定了内部的Block-level box如何布局，并且与这个区域外部毫不相干

### BFC布局规则

1.内部的Box会在垂直方向上一个接一个放置

2.Box垂直方向上的距离由margin决定，同属于同一个BFC的两个相邻的Box的margin会发生重叠（兄弟元素margin重叠问题）

3.每个Box的左外边缘（margin-left)， 与包含块的左边（contain box left）相接触(对于从左往右的格式化，否则相反)。即使存在浮动也是如此。除非这个元素自己形成了一个新的BFC。

4.BFC区域不会与float-box重叠（两列布局）

5.计算BFC高度时，浮动元素也参与计算

6.BFC是页面上的一个隔离的独立容器，容器里的元素不会影响到外部元素，反之亦然

### BFC开启方式

1.根元素

2.float不为none

3.position为absolute或fixed

4.overflow不为visible

5.display为inline-block, table-ceil, table-caption, flex, inline-flex

## 三列布局

三列布局的要求

1.中间优先加载

2.两边固定，中间自适应

### 圣杯布局

左右两列固定200px中间列自适应

内容区三列，HTML结构先写中间列然后左列右列

中间列width: 100%;

三列全部浮动，内容区清除浮动

左列margin-left: -100%; 将左列提升到上一行最左侧

右列margin-left: -200px; 将右列提升到上一行最右侧

内容区padding: 0 200px; 为左右两列留出空间

左列position: relative; left: -200px;

右列position: relative; left: 200px;

### 双飞翼布局

左右两列固定200px中间列自适应

内容区三列，HTML结构先写中间列然后左列右列

中间列用warp包裹

wrap的width: 100%

三列全部浮动，内容区清除浮动

左列margin-left: -100%; 将左列提升到上一行最左侧

右列margin-left: -200px; 将右列提升到上一行最右侧

中间wrap padding: 0 200px; 为左右两列留出空间

与圣杯布局的区别是不使用定位

### flex布局

左右两列固定200px中间列自适应

内容区三列，HTML结构先写中间列然后左列右列

内容区display: flex;

左右两列width: 200px; 或flex-basis: 200px;

中间列flex-grow: 1; 或flex: 1;设置拉伸因子为1 或者width: 100%

三列设置order 左中右排列

### Grid布局

左右两列固定200px中间列自适应

内容区三列，HTML结构先写中间列然后左列右列

内容区

display: grid;

grid-template-columns: 200px auto 200px;

grid-template-areas: 'left center right';

中间列

grid-area: center;

## 绝对定位模拟固定定位

原理：绝对定位是相对于最先开启定位的祖先元素定位，若无，则相对于初始包含块定位

而浏览器默认滚动条并不是在html或body上，而是在初始包含块上

也就是说滚动滚动条移动了初始包含块从而导致了绝对定位元素的移动

所以将滚动条绑定body上就可以滚动滚动条不移动初始包含块，从而绝对定位模拟固定定位

```
html {
    overflow: hidden;
}
body {
    overflow: auto;
}
```

## 垂直排列兄弟元素margin重叠问题

原因BFC布局规则：属于同一BFC下，垂直排列的Box间距由margin决定，margin会重叠

解决方案：使兄弟Box属于不同的BFC

给其中兄弟元素裹上wrap，wrap overflow为hidden开启BFC

## 父子元素margin传递问题

当两个空的块级元素嵌套时，如果内部块设置有margin-top属性，那么内部块的margin-top属性会绑架父元素（即父元素也会出现相应的margin-top行为）

解决方案：父元素通过before伪元素与子元素隔开
```
#warp:before {
    content: "";
    display: table;
}
```

## 子元素浮动高度塌陷

伪元素after content: '' display: table;

## IE CSS hack

类内属性前缀法 和 条件注释法

用来设置不同IE版本对CSS的识别性

## 盒模型相关属性默认值

left top right bottom 默认值auto
width height 默认值auto
margin padding 默认值0
border-width 默认值medium

## 盒模型百分比属性

width height百分比是相对于包含块对应的width height取百分比

margin padding百分比是相对于包含块width取百分比

top left百分比是相对于包含块对应的height width取百分比

## 元素垂直水平居中方案

### 不使用定位

#### flex

容器：

display: flex;

justify-content: center;

align-items: center

#### Grid

容器：

display: grid;

justify-content: center;

align-items: center

### 使用定位

容器：相对定位

元素绝对定位

top left: 50%

transform: translate3D(-50%, -50%, 0)

或者利用绝对定位盒子的特性

水平方向上：left + right + width + padding + margin = 包含块的content-box

垂直方向上：top + bottom + height + padding + margin = 包含块的content-box

容器：相对定位

元素绝对定位

top left right bottom:0

margin: auto

前提：已知元素高宽

## CSS隐藏元素

### display:none;

不占据空间，无法响应自身事件

### position: absolute;+z-index : -9999;

不占据空间，无法响应自身事件

### overflow:hidden;

隐藏元素溢出部分，依然占据空间，但无法响应自身事件

### visibility:hidden;

依然占据空间，无法响应自身事件

### transform:scale(0,0);

依然占据空间，无法响应自身事件

### opacity:0;

透明度为0，依然占据空间，可响应自身事件

## px em rem vw vh vmin vmax

px：相对于显示器屏幕分辨率

em：是相对长度，相对于自身的font-size，chrome默认16px

rem：是相对长度，相对于根标签的font-size

vw：相对视口宽度的1%

vh：相对视口高度的1%

vmin：相对视口高宽中较小值的1%

vmax：相对视口高宽中较大值的1%

## 响应式布局方案

### 媒体查询

例如：

```
/* iphone6 7 8 plus */
@media screen and (max-width: 414px) {
    body {
        background-color: blue;
    }
}
```

### 百分比布局

### rem布局

rem布局原理：不改变CSS像素大小，改变不同设备上所占CSS像素的个数

### viewport布局

viewport布局原理，改变CSS像素和物理像素的比例，不改变元素所占CSS像素的个数

### vw/vh布局

### flex布局

### grid布局

## CSS画底为40px高为40px的等腰三角形

```
#test {
    width: 0px;
    height: 0px;
    border-width: 40px 20px;
    border-color: transparent transparent red transparent;
    border-style: solid;
}
```

## CSS画一个扇形

```
#test {
    width: 0px;
    height: 0px;
    border-width: 40px 20px;
    border-color: transparent transparent red transparent;
    border-style: solid;
    border-radius: 20px;
}
```



# JavaScript相关

## JS实现函数柯里化+偏函数组合应用

什么是柯里化？

多参数函数转换为一系列单参数函数的技术

什么是偏函数？

多函数参数，每次应用其一个或多个参数，但不是全部参数，在这个过程中创建一个新函数，这个函数用于接受剩余的参数。

```
    // js实现函数柯里化+偏函数
    function curryPartial(fn, args) {
      // 获取函数形参个数
      const length = fn.length
      // 获取实参数组
      args = args || []
      // 返回柯里化函数
      return function () {
        // 实参数组整合
        const argsArray = args.concat(Array.from(arguments))
        // 如果实参个数小于形参个数
        if (argsArray.length < length) {
          // 继续整合
          return curryPartial.call(this, fn, argsArray)
        } else {
          // 当实参整合完成调用函数
          return fn.apply(this, argsArray)
        }
      }
    }
    var fn = curryPartial(function (a, b, c) {
      console.log([a, b, c]);
    });

    fn("a", "b", "c") // ["a", "b", "c"]
    fn("a", "b")("c") // ["a", "b", "c"]
    fn("a")("b")("c") // ["a", "b", "c"]
    fn("a")("b", "c") // ["a", "b", "c"]
```
## JS中为什么 0.1+0.2 !== 0.3

JS中Number数据类型遵循IEEE 754标准

64位二进制从左往右依次为：

第63位：符号位，0表示正数，1表示负数(s)

第62位到第52位：储存指数部分（e）

第51位到第0位：储存小数部分（即有效数字）f

但JS的最大安全数 Number.MAX_SAFE_INTEGER = Math.pow(2,53)-1

因为二进制有效数字总是 1.xxxxxxx (xxxxxxx为尾数部分f，有效数字首位默认为1}

因此JS二进制有效数字长度为53（64位浮点的前52位+被省略的1位）

在运算 0.1+0.2 的过程中两处产生精度损失

1.进制转换

0.1转二进制0.0001100110011001100110011001100110011001100110011001101(无限循环)

0.2转二进制

0.001100110011001100110011001100110011001100110011001101(无限循环)

超过IEEE 754尾数位置限制将被截取

2.对阶运算

由于指数位数不相同，运算时需要对阶运算 这部分也可能产生精度损失

最终造成 0.1+0.2 !== 0.3 的结果

注：浮点数值的最高精度是 17 位小数，因此0.1.toPrecision(17) = 0.100000000000000000导致 0.1 还是 0.1

解决方法:
```
function add(num1, num2) {
    const num1Digits = (num1.toString().split('.')[1] || '').length;
    const num2Digits = (num2.toString().split('.')[1] || '').length;
    const baseNum = Math.pow(10, Math.max(num1Digits, num2Digits));
    return (num1 * baseNum + num2 * baseNum) / baseNum;
}
```

## 隐式转换

转换布尔类型为false：NaN null undefined +0 -0 '空串' 以及H5废弃的document.all   （7）

转换为Number为0：false '空串' null      (3)  注意undefined转换为NaN

转换为String，注意null，undefined不是调用toString()方法，而是直接返回 'null'  'undefined'

判断的基本规则：

1.对象 == 基本数据类型
toPrimitive(对象) ： 对象.valueOf().toString()

2.布尔值 == 任何类型
Number(布尔值)：将布尔值转化为数字

3.数字 == 字符串
Number(字符串)：将字符串转化为数字

4.要比较相等性之前，不能将 null 和 undefined 转换成其他任何值。

5.undefined == null
true

```
console.log(1 + 'true'); // 1true
console.log(1 + true); // 2
console.log(1 + undefined); // NaN
console.log(1 + null); // 1
console.log('2' > 10); // false
console.log('2' > '10'); // true 依次比的是unicode编码
console.log('abc' > 'aad'); // true
console.log(NaN == NaN); // false NaN和任何值比都是false
console.log(undefined == null); // true
console.log([1,2] == '1,2') // true 数组的valueOf().toString()方法转字符串
console.log([] == 0) // true 数组的valueOf().toString()空串转数字为0
consolo.log(![] == 0) // true []经过Boolean()为true取反为false
console.log({} == !{}) // false {}布尔为true取反为false，Number后为0 {}valueOf().toString()为'[object Object]'Number()后为NaN
console.log({} == {}) // false 引用不同
console.log([] == []) // false 引用不同
console.log(null == 0) // false 要比较相等性之前，不能将 null 和 undefined 转换成其他任何值。
console.log('true' == true) // false，true转数字为1 'true'转数字为NaN
```

```
const a = ???
if (a == 1 && a == 12 && a == 23) {
    console.log(true)
}
```

引用类型隐式转换为原始类型流程：

调用toPrimitive()内部函数

1.是否为原始类型？是则返回

2.否则调用valueOf()方法，返回值是否为原始类型？是则返回

3.否则调用toString()方法，返回值是否为原始类型？是则返回

4.否则，抛出错误

所以我们可以通过定义引用对象的valueOf()或toString()方法来覆盖Object.prototype的方法

```
const a = {
    value: -10,
    valueOf() {
        return this.value += 11
    }
}
if (a == 1 && a == 12 && a == 23) {
    console.log(true)
}
```

## 包装类

JS三个包装类：Number() String() Boolean()
作用：将基本数据转换为引用数据类型，

当我们对一些基本数据类型的值去调用属性和方法时，浏览器会临时使用包装类将其转换为对象，然后在调用对象的属性和方法

调用完以后，再将其转换为基本数据类型

## this指向

解析器在调用函数每次都会向函数内部传递进一个隐含的参数,这个隐含的参数就是this，this指向的是一个对象

这个对象我们称为函数执行的 上下文对象，根据函数的调用环境的不同，this会指向不同的对象

1.以函数的形式调用时，this指向window

2.以方法的形式调用时，this就是调用方法的那个对象

3.当以构造函数的形式调用时，this就是新创建的实例对象

4.使用call() apply() bind()调用时，this是指定的第一个参数

5.在绑定监听时，给谁绑定，回调函数中的this就是谁

6.箭头函数自身没有this，箭头函数的this继承的是外部函数的this

## call() apply() bind()的区别

call和apply改变了函数的this上下文后便执行该函数,而bind则是返回改变了上下文后的一个新函数。

call和apply之间的差别在于参数的区别，call和apply的第一个参数都是要改变上下文的对象，

而call从第二个参数开始以参数列表的形式展现，apply则是将参数放在一个数组或类数组里面作为它的第二个参数。

## new的执行过程

1.创建新的实例对象

2.给新建实例对象属性赋值，其__proto__隐式原型指向其构造函数的prototype显式原型

3.this上下文指向新建的实例对象

4.执行构造函数

5.构造函数有无return
无return（即return undefined）或return类型为基本类型，则最终return还是新建的实例对象
若return为一个引用类型，则最终return这个引用类型



## DOM增删改查

### 查

#### 通过方法获取

##### 1.获取单个元素

getElementById() querySelector()

##### 2.获取HTMLCollection动态伪数组

getElementsByClassName() getElementsByTagName()

##### 3.获取NodeList静态伪数组

getElementsByName() querySelectorAll()

#### 通过属性获取

##### 1.获取子节点/子元素

子节点：childNodes(NodeList动态) firstChild lastChild

子元素：children(HTMLCollection)

##### 2.获取父节点

parentNode

##### 3.兄弟节点/兄弟元素

previousSibling nextSibling

previousElementSibling nextElementSibling

### 增

createElement() createTextNode()

父节点.appendChild(子节点)

父节点.insertBefore(新节点, 旧节点)

createDocumentFragment()文档片段

### 改

父节点.replaceChild(新节点, 旧节点)

innerHTML

### 删

父节点.removeChild(子节点)

自删：子节点.parentNode.removeChild(子节点)

## DOM绑定/解绑监听

以click事件为例

DOM0级

Element.onclick = () => {}

优点：兼容性好

缺点：只能为一个元素的一个事件绑定一个监听函数，如果绑定多个，则后绑会覆盖先绑

解绑：赋值null

DOM2级

Element.addEventListener(('click', () => {}, false))

参数：

1.事件的字符串，不要on

2.回调函数，当事件触发时该函数会被调用

3.是否在捕获阶段触发事件，需要一个布尔值，默认都传false

优点：可以为一个元素的一个事件绑定多个回调函数，多个回调函数按绑定顺序执行

缺点：兼容性不好，不支持IE8及以下

解绑：removeEventListener，三个参数必须全部一致才能解绑

IE8及以下可使用attachEvent()来给元素同一事件绑定多个监听

参数：

1.事件的字符串，要on

2.回调函数，当事件触发时该函数会被调用

与addEventListener的区别：

先绑定后执行，this上下文不是指向绑定元素而是window

解绑：detachEvent()，两个参数必须全部一致才能解绑

## 事件流

事件流分为三个阶段：捕获阶段 目标阶段 冒泡阶段

### 捕获阶段

从最外层祖先元素，向目标元素进行事件的捕获，默认此时不会触发事件

（addEventListener第三个参数为false, attachEvent没有第三个参数因为IE8及以下没有捕获阶段）

### 目标阶段

事件捕获到目标元素，捕获结束开始在目标元素上触发事件

### 冒泡阶段

事件从目标元素向他的祖先元素传递，依次触发祖先元素上的事件

阻止冒泡：event.stopPropagation()

## 事件委派（利用事件冒泡）

将统一的事件绑定给元素的共同祖先元素，这样当后代元素上的事件被触发时，会冒泡到祖先元素，从而通过祖先元素的响应函数来处理事件

通过事件委派可以减少事件绑定的次数，提高程序的性能

但是注意：祖先元素不会直接处理事件，而是根据event.target得到发生事件的后代元素，通过这个后代元素调用回调函数

## JS引擎如何管理内存

### 内存的生命周期

1.分配内存，得到使用权

2.存储数据进行反复操作

3.释放内存空间

### 释放内存

栈内存使用一级缓存，堆内存使用二级缓存

1.局部变量：函数执行完自动释放

2.对象：称为垃圾对象（无变量引用 ） => 垃圾回收机制回收

## JavaScript垃圾回收机制

### 标记清除

当变量进入JS执行栈环境标记为 '进入环境' ，标记为'进入环境'的变量不可被回收

当变量从JS执行栈出栈，则标记为'离开环境'，离开环境的变量可以被回收

### 引用清除

堆对象被变量引用的次数为0时，回收其占用的内存空间

引用清除存在循环引用的问题

```
const A = {}
const B = {}
A.b = B
B.a = A
```
A, B二个对象的堆内存的引用次数均为2，会一直存在于内存中
解决：赋值为null，不再引用

IE9把DOM和BOM转换成真正的JS对象了，所以避免了这个问题。

## 原型与原型链

### 显式原型与隐式原型

每个函数对象都有 prototype，它默认指向一个 Object 实例对象，即 显式原型 prototype

每个实例对象都有__proto__，即隐式原型，__proto__  指向其构造函数的 prototype

### 原型链

原型链即隐式原型链

实例对象的隐式原型指向其构造函数的显式原型

注意点：

1.Object和Function都是函数，所有函数都是Function的实例，所以其隐式原型均指向Function.prototype

2.Object.prototype.__proto__ = null

当访问一个实例对象的属性时

1.先在实例对象自身的属性中查找，找到返回，否则

2.沿着原型链向上查找，找到返回，否则

3.返回 undefined

## instanceof

A instanceof B

在同一全局环境下，A的隐式原型链是否经过B的显式原型

## 预解析

var 提前申明，但不赋值，执行到才赋值

function 提前声明且定义

## 执行上下文

### 全局执行上下文

1.在执行全局代码前将window确定为全局执行上下文对象

2.预解析
var 提前声明不赋值，添加为window的属性
function 提前声明且定义，添加为window的方法
this上下文指向window

3.压栈，执行全局代码

### 函数执行上下文

1.在调用函数准备执行函数体之前，创建对应的函数执行上下文对象

2.预解析
形参，arguments，this赋值，添加为函数执行上下文的属性
var 提前声明不赋值，添加为函数执行上下文的属性
function 提前声明且定义，添加为函数执行上下文的方法

3.压栈，执行函数代码

## 执行上下文栈

1.在全局代码执行前，JS引擎会创建执行栈来存储所有的执行上下文对象

2.在全局执行上下文确定后，将其压栈

3.在函数执行上下文创建后，将其压栈

4.在当前函数执行完后，将栈顶出栈，仍然在内存中，等待垃圾回收机制回收

5.所有代码执行完后，栈中只剩window

## 作用域

JavaScript采用的是词法作用域（静态作用域）

分类：全局作用域，函数作用域，ES6块级作用域

作用：隔离变量，不同作用域下同名变量不会有冲突

## 作用域链

通过词法环境的对外部词法环境的引用（scope）将作用域链起

变量可通过作用域链逐层向上查找

## 闭包

### 什么是闭包？

高程：有权访问另一函数作用域中的变量的函数
MDN：函数以及其对外部词法环境的引用捆绑称为闭包

### 闭包的作用

1.延长局部变量的生命周期

2.让函数外部可操作函数内部的数据

### 闭包可能导致的问题

内存泄漏 解决：即时释放引用的外部词法环境

## 进程与线程

### 进程

进程是资源（CPU、内存等）分配的基本单位，它是程序执行时的一个实例。程序运行时系统就会创建一个进程，并为它分配资源

### 线程

线程是进程内的一个独立执行单元，是程序执行的一个完整流程，也是CPU最小的调度单元

### 关系

应用程序必须运行在一个进程的某个线程上

一个进程至少有一个运行的线程，也就是主线程

一个进程多线程运行时，线程之间数据共享

多个进程之间的数据不能直接共享

## 词法环境

词法环境主要分为两个组成部分

### 环境记录

登记变量，函数，模块的地方

#### 声明式环境记录

用来记录直接有标识符定义的元素，比如变量、const、let、class、module、import以及函数声明

函数环境记录：用于函数作用域。

模块环境记录：模块环境记录用于体现一个模块的外部作用域，即模块export所在环境。

#### 对象式环境记录

主要用于with和global的词法环境

### 对外部词法环境的引用(outer)

它是作用域链能够连起来的关键

## ES5严格模式语法和行为的改变

1.必须用var声明变量

2.禁止自定义函数this指向window

3.创建eval作用域

4.对象不能有重名属性

## let与const

### let

用于声明一个变量

特点：

1.拥有块级作用域

2.不能重复声明

3.没有预解析，存在暂时性死区

4.全局声明不会成为window的属性

### const

用于声明一个常量

特点：

1.不能修改

2.拥有块级作用域

3.不能重复声明

4.没有预解析，存在暂时性死区

5.全局声明不会成为window的属性

## ...三点运算符

### ...剩余参数

### ...扩展运算符

## 浅拷贝与深拷贝

### 浅拷贝

拷贝指针，修改拷贝后的数据会影响原数据，使得原数据不安全

### 深拷贝

拷贝的时候生成新数据，修改拷贝后的数据不会影响原数据

### JSON.parse(JSON.stringify(result))

缺点：不能对undefined，函数，symbol进行深拷贝

### 递归实现深拷贝

1.判断数据类型

typeof 注意：typeof判断array,object,null均返回'object'

Object.prototype.toString.call(param).slice(8, -1)

Array.isArray()

A instanceof B

2.遍历递归

```
    function deepCopy(obj) {
      if (typeof obj !== 'object' || obj === null) {
        return obj
      }
      const result = obj instanceof Array ? [] : {}
      for (const key in obj) {
        if (obj.hasOwnProperty(key)) {
          result[key] = deepCopy(obj[key])
        }
      }
      return result
    }
```

## 如何判断是否是数组

### instanceof

缺陷：instanceof假定只有一个全局环境，如果网页中包含多个框架，那实际上就存在两个以上不同的全局执行环境，从而存在两个以上不同版本的Array构造函数。

如果你从一个框架向另一个框架传入一个数组，那么传入的数组与在第二个框架中原生创建的数组分别具有各自不同的构造函数。

### param.constructor === Array

缺陷：construcor属性可改写

### Object.prototype.toString.call(param).slice(8, -1)

### Array.isArray(param)

## 数组去重

```
      for (let i = 0; i < arr.length; i++) {
        if (arr.indexOf(arr[i]) !== i) {
          arr.splice(i, 1)
          i--
        }
      }
      return arr
```

`Array.from(new Set(arr))`

`arr.filter((item, index) => arr.indexOf(item) === index)`

`arr.reduce((prev, cur) => prev.includes(cur) ? prev : [...prev, cur], [])`


## 判断一个对象是否是空对象

`String(obj) === '[object Object]' && Reflect.ownKeys(obj).length === 0`

Reflect.ownKeys() 为 Object.getOwnPropertyNames() 与 Object.getOwnPropertySymbols() 二者 concat() 之后的数组

## 伪数组转数组

### `[...param]`(有限)

拥有可迭代属性接口，也就是 Symbol.iterator 的伪数组对象（如arguments,  NodeList,  HTMLCollection）才可用

对于自定义的伪数组，若没有添加 Symbol.iterator 则会报错

### Array.prototype.slice.call(param)

### Array.from(param) 接受伪数组和可迭代对象

## super关键字 与 super()

### super关键字

super是指向当前对象的原型的一个指针，实际上就是Object.getPrototypeOf(this)的值

super在函数简写写法内才有效，否则会报错

```
const person = {
    say() {
        return 'Hi'
    }
}
const friend = {
    say() {
        return super.say() + 'friend'
    }
}
Object.setPrototypeOf(friend, person)
```
### super()

派生类构造器中

super(params) 相当于 基类.call(this, params)

所以派生类构造器中的super()是用来初始化this

super()使用注意点

1.你只能在派生类中使用super()。若尝试在非派生的类（即：没有使用extends关键字的类）或函数中使用它，就会抛出错误。

2.在构造器中，你必须在访问this之前调用super()。由于super()负责初始化this，因此试图先访问this自然就会造成错误。

3.唯一能避免调用super()的办法，是从类构造器中返回一个对象。

## class关键字

class关键字是以ES5组合继承为基础的一个语法糖，但是它和组合继承又有区别

1.组合继承的自定义function构造函数存在变量提升，而类声明类似于let，没有变量提升，存在暂时性死区

2.类声明中的所有代码会自动运行在严格模式下，且无法退出严格模式

3.类的所有实例方法都是不可枚举的，而自定义构造函数只有通过Object.defineProperty()才能将方法改为不可枚举

4.类的所有实例方法内部都没有constructor，使用new调用类的实例方法会报错

5.调用类构造器时，不加new会报错

6.在类的实例方法内部尝试重写类名会报错

## Promise

### 什么是Promise

Promise是ES6新增的对于JS异步编程的一种新的解决方案，可以解决回调地狱问题

从语法上来说：Promise是一个构造函数

从功能上来说：Promise实例用来封装异步操作，并可获取其结果

### Promise的三种状态

Pending初始化状态，fulfilled成功状态，rejected失败状态

### Promise的API

Promise.resolve()：返回一个成功状态的promise

Promise.reject()：返回一个失败状态的promise

Promise.all()：多个 Promise 任务同时执行。如果全部成功执行，则以数组的方式返回所有 Promise 任务的执行结果。 如果有一个 Promise 任务 rejected，则只返回 rejected 任务的结果。

Promise.race()：多个 Promise 任务同时执行，返回最先执行结束的 Promise 任务的结果，不管这个 Promise 结果是成功还是失败

Promise.prototype.then()：注册回调

Promise.prototype.catch()：捕获异常

### 如何让Promise.all()在抛出异常后依然有效?

将传入 Promise.all 的数组进行遍历，如果 catch 住 reject 结果，直接返回，这样就可以在最后结果中将所有结果都获取到

ES11：Promise.settled()

## 简述箭头函数

1.箭头函数本身没有this，箭头函数的this继承的是外部函数的this

2.箭头函数没有prototype

3.箭头函数没有construct内部方法，不能用new调用

什么时候使用箭头函数？

非对象的方法且不用做构造函数时，使用箭头函数

## for in 和 for of 和 Object.keys()的区别

### for in

1.for in遍历对象以及原型链上的可枚举属性

2.如果用于遍历数组，除了遍历其元素外，还会遍历数组对象自定义的可枚举属性及其原型链上的可枚举属性

3.遍历对象返回的属性名和遍历数组返回的索引都是 string 类型

### for of

1.for of遍历可迭代对象（String, Array, Map, Set, arguments, HTMLCollection, Nodelist）

2.遍历数组后输出的结果为元素的值，而非索引

```
// 如果要遍历对象，可与 Object.keys 配合
var person = {
    name: 'June',
    age: 17,
    city: 'guangzhou'
}
for(var key of Object.keys(person)) {
    console.log(person[key]); // June, 17, guangzhou
}

// 配合 entries 输出数组索引和值/对象的键值
var arr = ['a', 'b', 'c'];
for(let [index, value] of Object.entries(arr)) {
    console.log(index, ':', value);
    // 0:a, 1:b, 2:c
}
var obj = {name: 'June', age: 17, city: 'guangzhou'};
for(let [key, value] of Object.entries(obj)) {
    console.log(key, ':', value);
    // name:June,age:17,city:guangzhou
}
```

### Object.keys()

1.返回对象自身可枚举属性组成的数组

2.不会遍历对象原型链上的属性以及 Symbol 属性

3.如果用于遍历数组，除了遍历其元素外，还会遍历数组对象自定义的可枚举属性

4.遍历对象返回的属性名和遍历数组返回的索引都是 string 类型

# Web相关

## 同源政策

同源政策的目的，是为了保证用户信息的安全，防止恶意的网站窃取数据。

同源：同协议，同域名，同接口

## Ajax

```
    // 手写Ajax
    var xhr = new XMLHttpRequest()
    xhr.open('post', 'http://localhost:3000')
    xhr.send(obj)
    xhr.onreadystatechange = () => {
      // Ajax状态码
      // 0：请求未初始化，未open
      // 1：请求初始化未发送，open未send
      // 2：请求已发送
      // 3：请求正在处理
      // 4：请求已经完成
      if (xhr.readyState === 4 && xhr.status === 200) {
        console.log(xhr.responseText)
      }
    }
```

## 跨域的解决方案

### 封装jsonp

它不属于Ajax请求，利用script标签可以向非同源地址发送请求

```
    // 手写jsonp
    function jsonp(configObj) {
      const fnName = configObj.callbackName
      window[fnName] = configObj.success
      const scriptNode = document.createElement('script')
      scriptNode.src = `${configObj.url}?callback=${fnName}`
      document.body.appendChild(scriptNode)
      scriptNode.onload = () => {
        document.body.removeChild(scriptNode)
        window[fnName] = null
      }
    }
```

### CORS跨域资源共享

#### 简单请求

只要同时满足以下两个条件就属于简单请求，简单请求会跳过预检请求

条件1：

Method为 GET, HEAD, POST 之一

条件2：

Content-Type为 text/plain, multipart/form-data, application/x-www-form-urlencoded之一

请求中的任意 XMLHttpRequestUpload 对象均没有注册任何事件监听器

#### 预检请求

```
let express = require('express')
let app = express()
let whiteList = ['http://localhost:3000'] //设置白名单
app.use(function(req, res, next) {
  let origin = req.headers.origin
  if (whiteList.includes(origin)) {
    // 设置哪个源可以访问我
    res.setHeader('Access-Control-Allow-Origin', origin)
    // 允许携带哪个头访问我
    res.setHeader('Access-Control-Allow-Headers', 'name')
    // 允许哪个方法访问我
    res.setHeader('Access-Control-Allow-Methods', 'PUT')
    // 允许携带cookie
    res.setHeader('Access-Control-Allow-Credentials', true)
    // 预检的存活时间
    res.setHeader('Access-Control-Max-Age', 6)
    // 允许返回的头
    res.setHeader('Access-Control-Expose-Headers', 'name')
    if (req.method === 'OPTIONS') {
      res.end() // OPTIONS请求不做任何处理
    }
  }
  next()
})

```
### postMessage()

postMessage是HTML5 XMLHttRequest Level 2中的 API, 并且为数不多跨域操作的window属性之一,它可用于解决以下方面的问题:

1.页面和其打开的新窗口的数据传递

2.多窗口之间消息传递

3.页面与嵌套的iframe消息传递

4.上面三个场景的跨域数据传递

postMessage()方法允许来自不同源的脚本采用异步方式进行有限的通信,可以实现跨文本档,多窗口,跨域消息传递

### node中间件代理

![](_v_images/20200716181300173_30521.png =884x)

### nginx反向代理

### Websocket

Websocket是HTML5的一个持久化的协议，它实现了浏览器与服务器的全双工通信，同时也是跨域的一种解决方案。WebSocket和HTTP都是应用层协议，都基于 TCP 协议。但是 WebSocket 是一种双向通信协议，在建立连接之后，WebSocket 的 server 与 client 都能主动向对方发送或接收数据。同时，WebSocket 在建立连接时需要借助 HTTP 协议，连接建立好了之后 client 与 server 之间的双向通信就与 HTTP 无关了。


## 浏览器内核(render进程)多线程

### 主线程

#### JS引擎线程与GUI渲染线程互斥

#### JS引擎线程（V8引擎中JS编译执行过程）

将要执行全局代码时，创建JS执行栈，创建全局执行上下文并进行压栈

当执行到函数时，创建函数执行上下文并进行压栈

V8引擎在拿到执行上下文后对其代码逐行做分词分析以及词法分析

分词分析就是将如 var a = 2; 拆分成 var, a, =, 2, ;,这样的原子符号

词法分析就是指：登记变量声明，函数声明（登记的地方为词法环境）

在分词结束后，V8会做代码解析，将分好的原子符号解析翻译成一个抽象语法树，在这一步时，若发现语法错误，则会报错不再往下执行

最后V8引擎生成CPU可执行的机器码

#### GUI渲染线程

负责渲染浏览器页面

渲染过程

1.解析HTML构建DOM树

2.解析CSS构建CSSOM

3.DOM树和CSSOM结合形成Render树

4.布局Render树，负责元素的尺寸和位置（回流）

5.绘制Render树（重绘）

6.将各层信息发送给GPU进程，GPU将各层合成，显示在页面上

CSS的加载会阻塞渲染

#### 重绘回流与硬件加速

元素的位置和尺寸的改变会引起回流和重绘，元素样式改变会引起重绘，影响浏览器性能

因为GPU是专门为处理图形而设计，所以它在速度和能耗上更有效率。

通过GPU硬件加速的方式（transform、opacity、filters），声明一个新的复合图层，它会单独分配资源，这样就不会影响默认复合图层(标准文档流以及position为absolute，fixed都属于默认复合层)，从而避免重绘与回流

注意:如果a是一个复合图层，而且b在a上面，那么b也会被隐式转为一个复合图层

在GPU渲染字体会导致抗锯齿无效。这是因为GPU和CPU的算法不同。因此如果你不在动画结束的时候关闭硬件加速，会产生字体模糊。

### Web API分线程

#### 定时器管理线程
#### DOM事件响应线程
#### 网络请求线程

## 浏览器数据本地存储方式

### Cookies

由于HTTP是无状态协议，Cookies的出现是为了保存HTTP状态

服务器发送请求set-cookie，浏览器保存Cookies之后同域名下的每次HTTP请求都会携带Cookies的信息

JS也可通过document.cookie读取和设置

Cookies的特点：

1.遵循同源政策

2.Cookies的大小限制在4KB

3.过多的Cookies会导致性能浪费，因为同一域名下的所有请求都会携带Cookies

4.一般由服务器生成，可设置过期时间

5.和服务器通信

### LocalStorage

H5新增的本地存储方案
一个可被用于访问当前源（ origin ）的本地存储空间的 Storage 对象。
```
localStorage.setItem('myCat', 'Tom');
let cat = localStorage.getItem('myCat');
localStorage.removeItem('myCat');
localStorage.clear();
```

LocalStorage的特点：

1.遵循同源政策

2.大小为5M左右

3.可以在Tab之间数据通信

4.保存的数据会一直存在内存，没有过期时间，除非主动清除

5.只用在客户端，不和服务器通信

### SessionStorage

H5新增的本地存储方案

与LocalStorage相比，只用于当前浏览器的一次会话，浏览器关闭，数据清空

```
sessionStorage.setItem('key', 'value');
let data = sessionStorage.getItem('key');
sessionStorage.removeItem('key');
sessionStorage.clear();
```

SessionStorage的特点：

1.遵循同源政策

2.大小为5M左右

3.每次Tab创建各自的SessionStorage

4.浏览器关闭，当前SessionStorage清空

5.只用在客户端，不和服务器通信

### IndexedDB

它是一个运行在浏览器上的非关系型数据库，它的大小是没有存储上限的。

IndexedDB的特点：

1.遵循同源政策

2.存储空间大，没有上限

3.异步操作，不会造成浏览器卡死

4.保存的数据会一直存在内存，没有过期时间，除非主动清除

5.只用在客户端，不和服务器通信

## HTML5 manifest 离线缓存

### 原理

第一次访问时，浏览器会根据manifest文件上的离线存储资源清单进行本地缓存，

之后的每次在线访问，浏览器会比较manifest文件是否修改

如果未修改，则浏览器直接调用离线缓存无需再发送请求

若修改，则浏览器重新下载更新离线存储资源

若是离线状态下访问，浏览器直接使用离线存储的资源

这使得用户在离线状态下也可访问站点的部分资源

### 使用

`<meta manifest = ‘demo.appcache’>`
这个属性指向一个manifest的文件，这个文件指明了当前页面哪些资源需要进行离线缓存

manifest配置文件分为三部分

1.CACHE MANIFEST

指出需要进行manifest的文件，声明的文件都将被下载缓存下来

2.NETWORK

默认为*，表示除了CACHE外的其它所有资源都需要联网请求

3.FALLBACK

表示替代资源，这些资源加载不到就替代加载哪些资源


### 离线缓存更新问题及解决方案

只有当manifest文件改变时，浏览器才会重新下载离线存储资源

但是在重新下载离线存储资源，页面加载已经开始了，若缓存更新尚未完成，浏览器还是会使用旧的缓存的资源。

解决方案：

添加事件监听，当监听到本地缓存更新后，进行重载页面，以达到更新的目的。

```
applicationCache.addEventListener("updateready", function(){
    applicationCache.swapCache();      // 手动更新本地缓存
    location.reload();    //重新加载页面页面
},true);
```

## 强制缓存与协商缓存

浏览器缓存主要分为 memory cache 内存缓存 和 disk cache 磁盘缓存

memory cach： 读取高效，但缓存持续性短，会随着进程的释放而释放，一旦关闭tab页面，内存中的缓存就被释放了

disk cache：读取比 memory cach 慢，但缓存保存在磁盘中。在所有浏览器缓存中，disk cache 覆盖面最大。

### 强制缓存

强制缓存不会向服务器发送请求，直接从缓存中读取资源

#### Expires (HTTP/1.0)

设置缓存文件过期时间，当缓存文件过期需要向服务器再次请求

`Expires: Wed, 25 Sep 2019 08:13:53 GMT`

Expires 是HTTP/1.0的产物，受制于本地时间，如果修改了本地时间可能会造成缓存失效

#### Cache-Control (HTTP/1.1)

Cache-Control是HTTP/1.1的产物，若 Expires 和 Cache-Control 同时存在，Cache-Control 的优先级更高

`Cache-Control: max-age=60`
max-age表示缓存文件过期时间，过期需要重新请求

`Cache-Control: s-maxage=60`
s-maxage只在proxy代理缓存中有效，优先级高于 Expires 和 Cache-Control: max-age

`Cache-Control: public`
public表示该资源为公共资源，可以被缓存在任何可以被缓存的地方（CDN，中间代理服务器，浏览器等等），可多用户共享

`Cache-Control: private`
private表示该资源为私有资源，只可以被浏览器缓存

`Cache-Control: no-store`
no-store表示浏览器每次都从服务器拿资源

`Cache-Control: no-cache`
no-cache表示并不是不缓存，而是客户端缓存内容，但用不用由协商缓存决定

`Cache-Control: max-stale=60`
max-stale表示容忍最大过期时间

`Cache-Control: min-fresh=60`
min-fresh表示容忍的最小新鲜度，如60，表示希望60s内获得新的响应

### 协商缓存

协商缓存是在强制缓存失效后，浏览器携带缓存标识向服务器发送请求，由服务器根据缓存标识确定是否使用缓存的过程

主要有两种结果：
1.协商缓存生效，返回304，使用缓存

2.协商缓存失败，返回200和请求数据，不使用缓存

#### Last-Modified/If-Modified-Since (HTTP/1.0)

当浏览器第一次请求资源时，服务器返回资源的同时，在 Response Header 中会有一个 Last-Modified 的 Header，Header值是这个资源在服务器上最后修改的时间

当浏览器下次请求该资源时，在 Requset Header 中会有一个 If-Modified-Since 的 Header，Header值为上次响应的 Last-Modified 的值

服务器再次收到对该资源的请求，会将 If-Modified-Since 的 Header值与该资源最后修改时间进行对比，若无变化，则响应304和Not Modified，直接从缓存中读取，若有变化，则响应200并返回新的资源

但是Last-Modified存在两个弊端

1.若在本地打开缓存文件，即使没有对缓存文件进行修改，也还是会造成 Last-Modified 的值被修改，服务器不能命中缓存，导致发送相同的资源

2.因为 Last-Modified 只能以秒计时，若在1s内做出对文件的修改，那么服务器会认为缓存命中，不会返回新的资源

既然根据修改时间来决定是否缓存尚有不足，那么可以使用HTTP/1.1的 Etag/If-None-Match 根据文件内容来判断

#### Etag/If-None-Match (HTTP/1.1)

Etag是服务器响应请求时，返回当前资源文件的一个唯一标识，由服务器生成，只要资源有变化，Etag就会重新生成

浏览器在下一次向服务器请求资源时，会将服务器上次返回的 Etag 值放到 Request Header 的 If-None-Match 里

服务器只需要比较 Etag 值是否一致，就能很好地判断资源相对于客户端是不是已经更新过了

如果 Etag 值不匹配，则以常规GET 200回包形式，将新的资源和新的 Etag 响应给客户端

如果 Etag 值匹配，则响应304，客户端直接使用本地缓存

#### 两种方法对比

1.首先在精度和优先级上 Etag 高于 Last-Modified

2.性能上 Etag 逊于 Last-Modified，毕竟一个 Last-Modified 只需要记录时间，而 Etag 要根据算法算出 Hash

### 缓存机制

强制缓存优先于协商缓存进行，若强制缓存失效，则进行协商缓存，协商缓存由服务器决定是否使用缓存

协商缓存成功，响应304直接使用缓存

协商缓存失败，返回200和请求的资源


### 用户行为对缓存策略的影响

1.打开网页，地址栏输入地址：查找 disk cache 中是否有匹配，有则使用，没有则发送网络请求

2.普通刷新F5：因为Tab并没有关闭，所以优先从 memory cache 中加载，其次是 disk cache

3.强制刷新Ctrl+F5：浏览器不使用缓存，请求为Cache-Contrl: no-cache，Pragma: no-cache，服务器直接返回200和最新内容


## 详述输入URL到页面渲染的过程

DNS域名解析  >>> TCP分包 >>> IP寻路 >>> 找到服务器IP >>> TCP三次握手建立连接 >>> 数据传输 >>> TCP四次挥手断开连接 >>>

浏览器解析数据 >>> GUI渲染线程 >>> 解析构建DOM树 >>> 解析构建CSSOM >>> 构建Render树 >>> 布局Render树（回流）>>>

绘制Render树（重绘）>>> 将各层信息传给GPU进程，渲染显示到页面

## 如何实现SEO优化

1.对网站的标题，关键字，描述精心设计

2.使用H5语义化标签

3.减少HTTP请求数量

4.利用浏览器缓存

5.减少重绘重排

## 详述回流和重绘优化

当对DOM元素的大小位置进行改动时，会发生回流，回流一定重绘

当对DOM元素的样式进行改动时，会发生重绘，重绘不一定回流

优化：减少对DOM元素的操作，可以将元素移除DOM树再变更，或者利用GPU硬件加速，构建新的复合层

## 防抖和节流

### 函数防抖

什么是函数防抖？事件在触发N秒后执行回调，如果在N秒内又被触发，则重新计时

```
    var timer = null
    var delay = 1000
    btn.onclick = () => {
      clearTimeout(timer)
      timer = setTimeout(() => {
        console.log('====================================');
        console.log('防抖');
        console.log('====================================');
      }, delay);
    }
```

### 函数节流

什么是函数节流？事件在触发N秒后执行回调，在N秒内再次触发无效

```
    var timer = null
    var delay = 1000
    var last = 0
    var now = null
    btn.onclick = () => {
      now = +new Date()
      if (now - last > delay) {
        clearTimeout(timer)
        timer = setTimeout(() => {
          console.log('====================================');
          console.log('节流');
          console.log('====================================');
        }, delay);
        last = now
      }
    }
```

# HTTP

## TCP/IP五层模型

![](_v_images/20200716183612303_14934.png =563x)

封装过程
![](_v_images/20200716183726302_16749.png =648x)

## OSI七层模型

![](_v_images/20200716194053038_16109.png =656x)

## TCP三次握手

第一次握手：客户端向服务端发送带有syn的数据包，此时客户端变为半打开状态，服务端接收到syn的数据包，服务端也变为半打开状态

第二次握手：服务端向客户端发送带有syn/ack的数据包，客户端接收到后变为established已建立连接状态

第三次握手：客户端向服务端发送带有ack的数据包，服务端收到后变为established已建立连接状态

## TCP四次挥手

第一次挥手：客户端数据传输完成后向服务端发送带fin的数据包，此时客户端进入半关闭状态，不再向服务端发数据，但可以接收服务端的数据

第二次挥手：服务端收到带fin的数据包后，此时服务端端进入半关闭状态，不再接收客户端数据，但可以向客户端发数据，并向客户端发送带ack的确认数据包

第三次挥手：服务端数据传输完成后，向客户端发送带fin的数据包

第四次挥手：客户端接收到带fin的数据包后，向服务端发送带ack的确认数据包，客户端在两个最长报文寿命周期后关闭，服务端在收到ack报文后关闭

## TCP为什么三次握手四次挥手

三次握手：为了防止已失效的连接请求报文段突然又传送到了服务端，因而产生错误

四次挥手：TCP全双工通信，客户端和服务端都存在收发两种状态

## TCP的流量控制

通过滑动窗口机制有效控制数据发送方的数据发送速率

发送窗口的上限值应该是拥塞窗口和接收窗口之间的最小值

## TCP的拥塞控制

四种算法：慢开始，快重传，快恢复，拥塞避免


## TCP UDP

首先TCP和UDP都是传输层的协议

### TCP

1.TCP是面向连接的，所以可靠性高，无丢包

2.因为TCP是面向连接的，所以会有延时，实时性较差

3.TCP首部开销20字节，开销大

4.TCP连接只能点到点

使用场景：一般用于文件传输，电子邮件，远程终端接入这类对数据准确性要求高，有连接需求的场景

### UDP

1.UDP是面向非连接的，所以可靠性差，可能有丢包

2.因为UDP是面向非连接的，无连接时间，所以实时性好

3.UDP首部开销8字节，开销小

4.UDP支持一对一，一对多，多对一，多对多相互通信

使用场景：一般用于即时通信，流式多媒体通信这种对于实时性要求较高，对丢包要求较低的场景


## HTTP状态码

### 1XX（信息性状态码）

表示接收的请求正在处理

100：继续

101：切换协议，请求者要求服务器切换协议，服务器已确认并准备切换

### 2XX（成功状态码）

表示请求正常处理完毕

200：成功

204：无内容，服务器成功处理了请求，但没有返回任何内容

206：部分内容，服务器成功处理了部分GET请求

### 3XX（重定向状态码）

表示需要进行附加操作以完成请求

301：永久重定向

302：临时重定向，按原有的方法请求重定向地址

303：查看其他位置，用GET方法定向获取请求的资源

304：未修改，自从上次请求后，请求的网页未修改过。服务器返回此响应，不会返回网页的内容

307：临时重定向，不指定用什么方法请求重定向地址

### 4XX（客户端错误状态码）

表示服务器无法处理请求

400：语法错误，请求报文存在语法错误

401：未授权，未通过认证

403：禁止，服务器拒绝请求

404：未找到，服务器未找到指定资源

405：方法禁用，禁用请求中的指定方法

### 5XX（服务器错误状态码）

表示服务器处理请求出错

500：服务器内部错误，服务器遇到错误无法完成请求

503：服务器目前不可用，超载或停机维护

## HTTP的方法

### GET：获取资源

### POST：主要用于提交数据

### PUT：上传文件

### HEAD：获得报文首部

### DELETE：删除文件

### OPTIONS：询问支持的方法

## GET和POST的区别

1.语义不同：GET用来获取数据，POST用来提交数据

2.数据位置不同：GET数据放在URL中，POST数据数放在请求体中，但二者都属于明文传输

3.数据大小不同：GET数据大小受限于浏览器和服务器，最长2048字节，POST无限制

4.数据类型不同：GET只接受ASCII字符，而POST没有限制

5.编码方式不同：GET只能进行URL编码，而POST支持多种编码

6.缓存不同：GET会被浏览器缓存，而POST不会，除非手动设置

7.分包不同：GET产生一个数据包，同时发送Header和Data，POST产生两个数据包，先发Header，响应100，再发Data
但也不是所有浏览器都会发两个包，FireFox就是例外只发一个包

## Cookie和Session的区别

### Cookie

Cookie是为了解决HTTP协议无状态的特点所作出的努力

浏览器第一次发送请求时，服务器设置set-cookie响应，通知浏览器保存Cookie，之后同一域名下的每次请求都会携带cookie

Cookie一般包括如下内容：

1.Key：设置Cookie的key

2.Value：key对应的value

3.Expires：设置过期时间，如果没有设置，则Cookie为会话期Cookie

3.Max-Age：设置Cookie过期时间，权重比Expires高

4.Domain：设置Cookie在哪个域名中有效，如果没有设置，则为当前域名不含子域名，若设置，则自动包含子域名

5.Path：在哪个路径下有效，包含子目录

6.HttpOnly：当这个值为True的时候，表示浏览器不能通过document.cookie更改Cookie的值，可以避免被XSS攻击更改Cookie的值

7.Secure：当这个值为True的时候，Cookie在HTTP中无效，在HTTPS中有效

8.SameSite：规定浏览器不能在跨域请求中携带Cookie，减少CSRF攻击

### Session

Session也是一种HTTP储存机制， 为无状态的HTTP提供持久机制;

Session是存在服务器的一种 用来存放用户数据的类HashTable结构。

浏览器第一次发送请求时，服务器自动生成了一HashTable和一SessionID来唯一标识这个HashTable，并将其通过响应发送到浏览器。浏览器第二次发送请求会将前一次服务器响应中的SessionID放在请求中一并发送到服务器上，服务器从请求中提取出SessionID，并和保存的所有Session ID进行对比，找到这个用户对应的HashTable。

### 二者区别

1.存储位置不同：
Cookie存在在客户端，Session存放在服务端

2.存储大小不同：
单个Cookie容量4KB，而Session大小没有限制（但为了服务器性能考虑，也不宜存放过多数据）

3.存储数据类型不同：
Cookie只支持ASCII字符串，并需要编码方式存储为Unicode或二进制数据，而Session支持任意类型数据

4.存储有效期不同：
Cookie可以设置过期时间长时间存储，而Session在客户端关闭或Session超时都会失效，但如果Cookie不设置过期时间，那Cookie为会话期Cookie

5.安全性不同：
Cookie存放在客户端，安全性较低，Session存放在服务器，安全性较高

6.对服务器压力不同：
Cookie存放在客户端，对服务器无压力，Session存放在服务器，每个用户都会生成一个Session，Session过多消耗服务器资源

7.域支持范围不同：
Cookie可通过设置Domain跨子域访问，Session不支持跨域名访问

## HTTPS

HTTPS = HTTP +TSL/SSL协议加密

HTTP属于明文传输，所以存在 信息窃听 信息篡改 信息劫持 的问题

而 TSL/SSL 利用非对称加密实现身份认证和密钥协商，对称加密采用协商的密钥对数据加密，基于散列函数验证信息的完整性。

非对称加密：客户端共享公钥，服务端掌握私钥，客户端信息只能服务端解密，客户端向服务器发送唯一信息

对称加密：服务器和客户端共享相同密钥，不同客户端密钥不同，服务端维护多个密钥，密钥协商是安全基础

散列算法：函数不可逆，对输入敏感，输出长度固定

HTTPS的工作流程

1.客户端向服务器发送一个HTTPS请求，默认443

2.服务器把事先配置好的公钥证书发送给客户端

3.客户端验证公钥证书：是否过期，与客户端站点是否匹配，是否被吊销，上一级证书是否有效，递归验证到根证书，验证通过继续，不通过显示警告

4.客户端使用伪随机数生成对称加密使用的对称密钥，然后用证书的公钥加密这个对称密钥，发送给服务器

5.服务器使用自己的私钥解密这个对称密钥，这样客户端和服务器拥有了相同的对称密钥

6.服务器使用对称密钥加密数据发送给客户端

7.客户端通过对称密钥解密服务器响应的数据

## HTTP与HTTPS的区别

1.HTTP明文传输，HTTPS加密传输

2.HTTPS需要SSL/TSL证书

3.HTTP默认端口80，HTTPS默认端口443

4.HTTPS更利于SEO

5.SSL/TSL加密在传输层与应用层之间，HTTP基于应用层

## HTTP2.0

### HTTP1.1存在的问题

#### 1.TCP数量限制

对于同一域名，TCP连接数的限制6~8个，为了解决数量限制，出现了 域名分片 技术：资源分域，将资源放在不同域名下（如二级子域名下）
缺点：每个TCP连接都需要DNS查询，三次握手等占用额外的CPU和资源

#### 2.线头阻塞问题

每个TCP连接同时只能处理一个请求，如果上一个请求未响应，则会阻塞后续请求响应

#### 3.Header内容过多，没有压缩优化方案

#### 4.为了尽可能减少请求数，需要做合并文件，雪碧图，资源内联等优化工作，造成单个请求延迟过高，且内联的资源不能有效地使用缓存机制


### HTTP2.0的优势

#### 1.二进制分帧

帧是数据传输的最小单位，以二进制传输代替原本的明文传输，无需再使用域名分片，合并文件，雪碧图，资源内联

#### 2.多路复用

每个TCP连接上，可以不断向对方发送数据帧，每帧的 stream identifier 标明这个帧属于哪个流，然后在对方接收时，根据 stream identifier 将同一流的所有帧组成一整块数据

流的概念实现了单连接上多请求-响应并行，解决了HTTP1.1的TCP数量限制，线头阻塞的问题

HTTP2.0只需要建立一个TCP连接

还可以对 stream 指定优先级，优先级越高的越先响应

#### 3.服务端推送

浏览器发送一个请求，服务器主动向浏览器推送与这个请求相关的资源，这样浏览器就不用发送后续请求

相比于HTTP1.1资源内联的优势在于：

1.客户端可以缓存推送的资源

2.客户端可以拒收推送的资源

3.推送资源可以由不同页面共享

4.服务器可以按照优先级推送资源

#### 4.Header压缩

使用HPACK算法压缩Header

# React相关

## React的优点

1.声明式编程

2.组件化编程

3.支持客户端和服务端渲染

4.高效：原因在于虚拟DOM和Diff算法

## 虚拟DOM与Diff算法

虚拟DOM本质上是一个轻量的JavaScript对象，它是真实DOM的一个副本

在setState之后创建新的虚拟DOM树，与旧的虚拟DOM树通过Diff算法进行比较

多次setState合并操作，记录比较差异，最终将差异绘制到真实DOM，进行局部更新

## Diff算法比对思路（在shouldComponentUpdate默认为true，未使用key的情况下）

逐层对树节点进行比对

![](_v_images/20200721161919639_22038.png =640x)
通过比对移除2节点下的5，在3节点下新增5

![](_v_images/20200721162203303_1206.png =640x)
若认为只需在2下移除4就错了，diff算法会依次比较兄弟节点，所以应该是2节点下移除4增加5，移除5增加6，移除6

这里就体现出key的作用了，若每个组件没有唯一key，则对于5，6两个组件会重新渲染造成性能浪费

若每个组件都有唯一ID，则只需在2下移除4

若有1000个兄弟节点，在没有key的情况下，你只删除第一个兄弟节点，会造成之后999个节点的重新渲染

![](_v_images/20200721162948694_13975.png =640x)
对于跨层级移动DOM，移除2，同时包括移除2下4，5，增加3，同时包括增加3下2，2下3，4，移除3

可以看到当一个父节点变化时，其下子节点会全部重新渲染

优化：
组件生命周期setState之后，组件本身会进入shouldComponentUpdate()，默认为true，即使没有数据修改，也会render

对于父组件下的子组件，只比父组件多一个componentWillReceiveProps，后面与父组件相同

1.可主动修改此函数，判断新旧数据是否改变，改变返回true，更新组件，否则返回false，不更新组件

2.使用pureComponent纯组件
纯组件重写了shouldComponentUpdate()，对组件的新/旧state和props中的数据进行浅比较, 如果都没有变化, 返回false, 否则返回true

# 算法相关

## 8大排序算法

```
    const array = [7, 8, 6, 6, 6, 4, 5, 2, 3, 1]

    // 1.冒泡排序：相邻两个元素相比较，若a > b则交换顺序，使得最大的元素冒泡到最顶端 时间复杂度 n²
    function bubble(array) {
      for (let i = 0; i < array.length - 1; i++) {
        for (let j = 0; j < array.length - 1 - i; j++) {
          if (array[j] > array[j + 1]) {
            const temp = array[j]
            array[j] = array[j + 1]
            array[j + 1] = temp
          }
        }
      }
      console.log('====================================');
      console.log('bubble', array);
      console.log('====================================');
    }
    // bubble(array)

    // 2.选择排序：每次循环默认首元素为最小元素，通过依次比较寻找最小元素的下标，最后将首元素与最小元素替换 时间复杂度 n²
    function select(array) {
      for (let i = 0; i < array.length - 1; i++) {
        let minIndex = i
        for (let j = i; j < array.length; j++) {
          if (array[minIndex] > array[j]) {
            minIndex = j
          }
        }
        if (minIndex !== i) {
          const temp = array[minIndex]
          array[minIndex] = array[i]
          array[i] = temp
        }
      }
      console.log('====================================');
      console.log('select', array);
      console.log('====================================');
    }
    // select(array)

    // 3.插入排序：每次将一个新元素插入到有序表中，得到一个length+1新的有序表 时间复杂度 n²
    function insert(array) {
      for (let i = 1; i < array.length; i++) {
        // 要插入的牌
        let key = array[i]
        // 有序表最大下标
        let j = i - 1
        // 要插入的牌和有序表的牌比，找到自己的位置
        while (j >= 0 && key < array[j]) {
          // length + 1
          array[j + 1] = array[j]
          j--
        }
        array[j + 1] = key
      }
      console.log('====================================');
      console.log('insert', array);
      console.log('====================================');
    }
    // insert(array)

    // 4.快速排序：先通过一趟排序将序列排列成左右两部分，左部分均比右部分小，再分别对左右两部分进行排序，直到有序 时间复杂度 nlogn
    function partition(array, low, high) {
      // 基准值
      const key = array[low]
      while (low < high) {
        // 在右边寻找比基准值小的数
        while (low < high && key <= array[high]) {
          high--
        }
        // 比基准值小的数移到左边
        array[low] = array[high]
        // 在左边寻找比基准值大的数
        while (low < high && key >= array[low]) {
          low++
        }
        // 比基准值大的数移到右边
        array[high] = array[low]
      }
      // 基准值排序后的正确位置确定
      array[low] = key
      // 输出基准值的正确位置
      return low
    }

    function quick(array, low, high) {
      if (high <= low) {
        return
      }
      const keyIndex = partition(array, low, high)
      // 比基准值小的左边进行递归快排
      quick(array, low, keyIndex - 1)
      // 比基准值大的右边进行递归快排
      quick(array, keyIndex + 1, high)
    }
    // quick(array, 0, array.length-1)

    // 5.堆排序：1.构造大顶堆 2.堆顶元素与末尾元素互换，最大元素沉底 3.调整顶堆 23232323重复 时间复杂度 nlogn
    function heapAdjust(array, current, size) {
      // 取出当前节点
      const key = array[current]
      // 从当前节点的左子开始
      let left = 2 * current + 1
      for (left; left < size; left = 2 * left + 1) {
        // 找出两子中较大的一个
        if (left + 1 < size && array[left] < array[left + 1]) {
          left++
        }
        // 如果子大于父节点，则父子交换
        if (array[left] > key) {
          array[current] = array[left]
          current = left
          array[left] = key
        } else break
      }
    }

    function heap(array, size) {
      // 构建初始大顶堆，从最后一个非叶子节点开始
      for (let left = parseInt(size / 2 - 1); left >= 0; left--) {
        // 调整顶堆
        heapAdjust(array, left, size)
      }
      // 取堆顶并调整
      for (let nextSize = size - 1; nextSize > 0; nextSize--) {
        const temp = array[0]
        array[0] = array[nextSize]
        array[nextSize] = temp
        heapAdjust(array, 0, nextSize)
      }
    }
    // heap(array, array.length)

    // 6.希尔排序：将序列分为gap组，对每组直接使用插排
    // gap/2，反复执行，当gap为1时，为同一组，使用插排，时间复杂度 nlogn
    function shell(array) {
      for (let gap = parseInt(array.length / 2); gap > 0; gap = parseInt(gap / 2)) {
        for (let i = gap; i < array.length; i++) {
          // 要插入的牌的下标为j
          // 序列最大下标为j-gap
          let j = i
          while (j - gap >= 0 && array[j] < array[j - gap]) {
            const temp = array[j]
            array[j] = array[j -gap]
            array[j -gap] = temp
            j -= gap
          }
        }
      }
      console.log('====================================');
      console.log(array);
      console.log('====================================');
    }
    // shell(array)

    // 7.归并排序：将数组分为左右两组分别排序再合并 时间复杂度 nlogn
    function merge(leftArr, rightArr) {
      const result = []
      while (leftArr.length > 0 && rightArr.length > 0) {
        if (leftArr[0] < rightArr[0]) {
          result.push(leftArr.shift())
        } else {
          result.push(rightArr.shift())
        }
      }
      return result.concat(leftArr).concat(rightArr)
    }
    function merge_sort(array) {
      const length = array.length
      if (length === 1) {
        return array
      }
      const mid = parseInt(length / 2)
      const leftArr = array.slice(0, mid)
      const rightArr = array.slice(mid)
      return merge(merge_sort(leftArr), merge_sort(rightArr))
    }
    // const mergeArr = merge_sort(array)
    // console.log('====================================');
    // console.log(mergeArr);
    // console.log('====================================');

    // 8.计数排序：通过额外的数组countArr记录待排序数组中各元素的个数，countArr的索引为待排序数组的值 时间复杂度 n + k
    function count(array) {
      // 获取待排序数组的最大值，也就是新建数组countArr的最大索引
      let max = array[0]
      for (let i = 1; i < array.length; i++) {
        max = array[0] > array[i] ? array[0] : array[i]
      }
      const countArr = new Array(max + 2).fill(0)

      for (let i = 0; i < array.length; i++) {
        countArr[array[i]]++
      }
      let index = 0
      for (let i = 0; i <= max + 1; i++) {
        for(let j = 0; j < countArr[i]; j++){
          array[index++] = i
        } 
      }
      console.log('====================================');
      console.log(array);
      console.log('====================================');
      
    }
    // count(array)
```


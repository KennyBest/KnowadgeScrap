`HTML`（Hyper Text Markup Language）。
# 1.语法
## 1.1 基础
### 1.1.1 结构
* 所有的`HTML`文件必须以`<!DOCTYPE html>`声明开始。
* 自身必须以`<html>`开始，以`</html>`结束。
* 只有在`<body>`和`</body>`内才会在浏览器中显示。

```html
<!DOCTYPE html>
<html>
  <head>
  </head>

  <body>  
  </body>
</html>
```  
### 1.1.2 常用标签
```HTML
<!-- Heading 标题 -->
    <h1>Heading h1</h1>
    <h2>Heading h2</h2>
    <h3>Heading h3</h3>
    <h4>Heading h4</h4>
    <h5>Heading h5</h5>
    <h6>Heading h6</h6>

    <!-- Paragraphs 段落 -->
    <p>This is a small paragraphs.</p>

    <!--  Links 链接-->
    <a href="https://kennybest.github.io/">陌洛凉</a>

    <p>
        <!-- Images 图片 -->
        <img src="weixin_logo.png" alt="" width="36px" height="36px">
    </p>
```
> 标题从`<h1>`到`<h6>`显示依次减弱  

## 1.2 元素
`HTML5`一个元素通常由一组开始标签和结束标签组成。**标签不是元素**。可以允许空元素和嵌套元素。
>推荐所有标签都是用小写，所有元素都应该有结束标签，空元素中的标签在标签名之后添加`/`来闭合。

## 1.3 属性
* 所有的元素都可以有属性
* 属性提供这个元素的额外信息
* 一般在开始标签中定义
* 键值对的形式存在
* 推荐使用小写字母来表示属性名
* 属性值推荐使用双引号括起来（非必需），如果属性值自身包含双引号时，整个属性可以使用单引号括起来

## 1.4 标题
浏览器会自动在标题的前后添加空白，不要用标题标签去让文字变大或变粗。  
`<hr>`元素，生成一条水平线用来分割内容。  
`<head>`元素通常用来定义文件标题、字符集、样式、链接、脚本等。

## 1.5 段落
`<p>`元素定义段落，浏览器自动会在段落前后添加空格。
`<br>`元素用来分割行。  
`<pre>`元素用来显示格式化文本，按编辑时样式显示。

## 1.6 样式
`style`属性用来设置元素的样式。属性内容以键值对形式设置，且每一项用`;`显示。

## 1.7 文本格式
文本格式元素  

|元素|作用|
|: -- :|: -- :|
|`<b>`|粗体|
|`<strong>`|重要显示|
|`<i>`|斜体|
|`<em>`|加重突显|
|`<mark>`|标记或高亮文本|
|`<small>`|小文本|
|`<del>`|显示删除线|
|`<ins>`|下划线|
|`<sub>`|下标|
|`<sup>`|上标|

## 1.8 引号元素、缩进元素
浏览器会自动在`<q>`元素两侧添加`"`。  
`<blockquote>`元素用来缩进。
`abbr`元素用来缩写。

```html
  <p><abbr title="Li Ling Jie">LLJ</abbr></p>
```  
`<address>`元素定义联系人信息，通常以斜体显示，浏览器会在元素的前后添加换行。
`<cite>`定义一项事物的标题，以斜体显示。  
`<bdo>`元素逆序显示文本。  

## 1.9 计算机代码元素

* `<kbd>`元素定义键盘输出
* `<samp>`元素定义简单输出
* `<code>`元素定义代码片段
* `<var>`元素定义一个变量  

## 1.10 颜色
`HTML`里面支持颜色名、RGB、HEX。  

[颜色名称](http://www.w3schools.com/colors/colors_names.asp)  

## 1.11 链接Links
`HTML`中链接不必须是文字，可以是任何一个元素。  
语法：

```html
<a href="url">link text</a>
```
>这里的href是目标地址，一个完整链接，包含`https://www.`或`http://www.`前缀。当不包含传输协议时即为本地相对地址链接。link text可以替换为任何元素。

这里可以通过style属性来修改显示颜色。  

`target`属性标明从哪里打开链接文件，
* `_blank` ：新的页面或视图打开链接文件
* `_self` ： 默认项 在当前页面打开
* `_parent` ： 以父层尺寸打开链接文件
* `_top` ： 以当前视窗全屏显示  

### 1.11.1 制作书签
* 先设置要跳转的元素`id`属性
* 使用链接设置跳转控制项 里面的href设置为#id即可

### 1.11.2 外部路径

## 1.12 图片Images
`<img>`元素定义了图片。支持png、gif、jpg格式。

* src ： 图片路径
* alt ： 图片显示名称
* width、height、style ：设置图片大小

> 声明图片元素时建议设置图片大小，否则在图片加载时网页会闪。大小建议通过style去设置

`usemap`属性关联`<map>`元素。**没弄懂**  

## 1.13 表格 Tables
`<table>`元素定义表格，`<tr>`行元素 `<th>`单个cell元素。`<td>`表格中的数据容器。

## 1.14 列表 Lists

### 1.14.1 无序列表 unordered list

```html
<ul>
  <li>Frist</li>
  <li>Second</li>
</ul>
```
无序列表前标记符号可通过style里面`list-style-type`属性来控制。
* disc：默认项 实心黑色圆点
* circle：空心圆点
* square：方形
* none：无  

### 1.14.2 有序列表 ordered list

```html
<!-- 有序列表 -->
  <ol>
    <li>Tpppppp</li>
    <li>Cmmmmmm</li>
    <li>Gkkkkkk</li>
  </ol>
```
通过`type`属性来改变标记体
* type="1" 默认项 数字开头
* type="A" 大写字母开头
* type="a" 小写字母开头
* type="I" 大写罗马数字
* type="i" 小写罗马数字

### 1.14.3 描述列表 Description Lists

`<dl>`定义描述列表，`<dt>`定义条项，`<dd>`定义描述。

```html
<!-- 描述列表 -->
    <dl>
      <dt>列表项</dt>
      <dd>描述语</dd>
      <dt>Milk</dt>
      <dd>- white cold drink</dd>
    </dl>
```
>列表可以嵌套列表，可以通过自定义style来处理

## 1.15 Block 和 Inline 元素
所有`HTML`元素都依据自己的类型有一个默认的显示方式，大部分元素的显示方式为block或inline方式。  

### 1.15.1 Block方式元素
每一个`block-level`元素都会从新的一行开始，并占满有效的宽度。
eg： `<div>`，`<h1>-<h6>`，`<p>`，`<form>` 。   
`<div>`元素多用来做其它元素的容器，没有必需设置的属性，大部分时候设置`style`和`class`。

### 1.15.2 Inline元素
不会新起一行，仅占用必要的宽度。
eg： `<span>`，`<a>`，`<img>`。  

`<span>`元素常用来作为一些文字的容器。  

## 1.16 class属性
`class`属性为具有相同类名的元素定义相同的`style`。

## 1.17 iframe元素  

`<iframe>`元素用来在网页里面是显示网页。  
* scr: 网页的url
* width、height：宽高 默认px显示，也可以使用百分比设置
* 默认有一个边框   

`<iframe>`元素可以被用来作为link的目标显示，link的`target`属性必须指向`iframe`的name属性。  

## 1.18 script
`<noscript>`用来在浏览器不支持脚本时为用户提供警示语。  

## 1.19 文件路径

 文件路径描述的是一个文件在web站点文件结构中位置。

 |路径|描述|
 |: -- :|: -- :|
 |test.png|和当前页在同一个位置|
 |images/test.png|在当前页文件夹中的images文件夹内|
 |/images/test.png|根目录下images文件夹中|
 |../test.png|在当前文件夹的上一级文件夹中|  

 相对路径 参照上表  
 绝对路径 完整的路径地址  

 ## 1.20 Head

 `<Head>`元素是metadata容器，在`<html>`与`<body>`之间。`metadata`通常定义文件的标题、字符集、样式、链接、脚本等。

 `<title>`元素：
 * 定义浏览器选项卡的标题
 * 当用户添加到收藏的时候提供了当前页的标题
 * 在搜索结果中显示标题

 `<meta>`元素用来标明文件基本信息。

 ```html
    <!-- 字符集 -->
     <meta charset="utf-8">
     <!-- 定义描述 -->
     <meta name="description" content="Sample HTML Code">
     <!--  定义搜索关键字 -->
     <meta name="keywords" content="HTML, CSS, XML">
     <!-- 定义作者 -->
     <meta name="author" content="Lucien Li">
     <!-- 设置定时刷新 -->
     <meta http-equiv="refresh" content="30">
     <!-- viewport 用来告诉浏览器如何控制网页尺寸和缩放 -->
     <meta name="viewport" content="width=device-width, initial-scale=1.0">
 ```  

 `<base>`用来为网页里面所有的相对路径定义基本路径和target。  

 ## 1.21 布局Layout
 布局四种方式：
 * HTML tables **不要使用多个table去布局**
 * CSS float property
 * CSS framework
 * CSS flexbox

 ## 1.22 响应式网页设计 Responsive Web Design
 为了更好在不同设备上显示。

 ## 1.23 HTML Entities && Symbols
 在`HTML`中如果想使用保留字必须用Entities替换。

 [保留字替换](http://www.w3schools.com/html/html_entities.asp)

# 2.HTML Forms

## 2.1 Forms介绍

 `<form>`元素声明一个用来收集用户输入的表单。表单元素包含其它的表单类型元素。表单元素是一系列不同的输入元素。  

`action`属性
  定义了当表单被提交时执行的动作。通常当用户点击提交按钮时表单数据被发送到服务器上一个网页。如果`action`属性被省略时，事件在当前页建立。  

`method`属性
明确指出提交数据时使用哪一种http请求方式（GET或POST）。

`name`属性  
所有的输入框在提交时都必须有一个名字，否则将不会被发送。

## 2.2 表单元素

1. `<select>`元素  定义了下拉列表； `<option>`定义了可被选择的一项；默认选中第一项，如果想预先设置选择，可以设置`selected`属性。

    ```html
    <!-- 下拉列表 -->
  <select class="s1" name="cars">
    <option value="volvo">Volvo</option>
    <option value="saab">Saab</option>
    <option value="fiat">Fiat</option>
    <option value="audi">Audi</option>
  </select>
    ```  

2. `<textarea>`元素定义了多行输入框。`rows`属性指明显示的行数，`cols`属性指明显示的宽度。

  ```html
  <!-- 定义了多行输入框 -->
    <p>
        <textarea name="message" rows="8" cols="80">multi-line input field。
        </textarea>
    </p>
  ```
3. `<button>`元素  

  ```html
    <button type="button" name="button1" onclick="alert('Hello World')">Hello World</button>
  ```  

4. `<datalist>`元素 为`<input>`元素提供一个默认的下拉列表选项。  仅h5，且不支持Safari和IE9（及之前）。

  ```html
  <div class="datalist">
      <input list="browsers" name="browser">
      <datalist class="datalist" id="browsers">
        <option value="IE"></option>
        <option value="Firefox"></option>
      </datalist>
      <input type="submit" name="submitB" value="提交">
    </div>
  ```

5. `<keygen>`元素提供一个验证用户的加密方式。会生成一个公钥和一个私钥，公钥发送给服务器，私钥保存到本地，公钥被用来生成一个客户端证书来验证用户。仅h5。  

6. `<output>`元素  

## 2.3 Input 类型

  ```html
  <div>
  <!-- 普通文本类型 -->
  Name:<input type="text" name="firstname">
  <br>
  <!-- 密码类型 密码输入框-->
  Password:<input type="password" name="psw">
  <br>
  <!-- 提交类型 一个提交按钮 -->
  <input type="submit" >
  <br>
  <!-- 重置按钮 -->
  <input type="reset">
  <br>
  <!-- 单选按钮 -->
  <input type="radio" name="gender" value="male" checked>Male<br>
  <input type="radio" name="gender" value="female"> Female <br>
  <!-- 多选框 -->
  <input type="checkbox" name="vehicle1" value="Bike">I have a bike
  <br>
  <input type="checkbox" name="vehicle2" value="Car">I have a car
  <br>
  <!-- 按钮 -->
  <input type="button" name="button00" value="Button">
  <br>
  <!-- 以下仅H5支持 -->
  <!-- 颜色 -->
  <input type="color" name="favcolor">
  <br>
  <!-- 日期 可以同max和min属性来设置最大最小日期-->
  <input type="date" name="bday">
  <br>
  <!-- 日期时间 -->
  <input type="datetime-local" name="bdaytime">
  <br>
  <!-- 邮件 不支持IE9及之前-->
  <input type="email" name="email">
  <br>
  <!-- 年月输入框 -->
  <input type="month" name="bdaymonth">
  <br>
  <!-- number类型输入框 -->
  <input type="number" name="quantity" min="1" max="5">
  <br>
  <!-- 范围输入框 -->
  0<input type="range" name="points" min="0" max="10">10
  <br>
  <!-- 搜索框 -->
  <input type="search" name="googlesearch">
  <br>
  <!-- 电话 仅支持Safari-->
  <input type="tel" name="usertel">
  <br>
  <!-- 时间 -->
  <input type="time" name="time">
  <br>
  <!-- url -->
  <input type="url" name="homepage">
  <br>
  <!-- 周/星期 -->
  <input type="week" name="week_year">
</div>
  ```  

## 2.4 属性
1. `value`属性标明输入框的初始值
2. `readonly`属性指明这个输入框只能读，不能改变
3. `disabled`属性指明这个输入框不可用 （不可选 不可点 值也不会被发送）
4. `size`属性指明宽度
5. `maxlength`属性指明输入框最大输入长度
6. `autocomplete`属性
7. `novalidate`属性只对`<form>`元素有效，在提交的时候不再验证表单数据
8. `autofocus`属性成为第一响应者
9. `form`属性指明一个输入框属于那几个表单
10. `formaction`属性
11. `formenctype`属性
12. `formmethod`属性
13. `formnoavlidate`属性
14. `formtarget`属性
15. `height`和`width`属性
16. `min`和`max`属性
17. `multiple`属性 允许用户可以选择多个值
18. `pattern`属性 指明正则表达式验证元素值
19. `placeholder`属性
20. `required`属性 再提交的时候必须要输入
21. `step`属性
> 从第6条开始仅支持h5

# 3.HTML5

# 4.HTML5 Graphics
## 4.1 Canvas
`<canvas>`元素是唯一绘图的容器，并且必须使用`JavaScript`实际绘图。创建画布:
```html
  <canvas id="myCanvas" width="300" height="300" style="border:1px solid #000000;"></canvas>
```   
可用于画直线、圆、矩形、绘制文字、图片、渐变层。

```html
<!--
      1. 找到画布canvas元素
      2. 使用getContext()获取内置绘画对象
      3. 开始绘画
    -->
    <script type="text/javascript">
      var c = document.getElementById("myCanvas");
      var ctx = c.getContext("2d");
      // 画直线
      // moveTo(x,y)定义直线起始坐标
      ctx.moveTo(0,0);
      // lineTo(x,y)定义结束坐标
      ctx.lineTo(300, 300);
      ctx.stroke();

      // 画圆
      // beginPath() 开始路径
      ctx.beginPath();
      // arc(x,y,r,startangle,endangle) x,y 为圆心点坐标
      ctx.arc(150,150,40,0,2*Math.PI);
      ctx.stroke();

      // 写文字
      /*
      1. 设置字体
      2. fillText(text,x,y) -- 实体文字 或者 strokeText(text,x,y) --镂空文字
      */
      ctx.font = "30px Arial";
      // 设置颜色
      // ctx.fillStyle = "red";
      // 设置文字模式
      // ctx.textAlign = "center";
      ctx.fillText("Hello World",10,50);
      ctx.strokeText("Hello World",10,90);

      var c2 = document.getElementById('gradient');
      ctx2 = c2.getContext("2d");
      // 渐变层
      // 线性渐变层
      // var grd = ctx2.createLineGradient(0,0,200,0);
      // grd.addColorStop(0,"red");
      // grd.addColorStop(1,"white");
      // // 渐变层填充
      // ctx2.strokeStyle = grd;
      // ctx2.fillRect(10,10,150,80);

      // 放射性渐变层
      var grd2 = ctx2.cteateRadialGradient(75,50,5,90,60,100);
      grd2.addColorStop(0,"red");
      grd2.addColorStop(1,"white");

      ctx2.fillStyle = grd;
      ctx2.fillRect(10,10,150,80);

      // 绘制图片
      ctx.drawImage(img,10,10);
    </script>
```  

## 4.2 SVG
  SVG(Scaleable Vector Graphic) 被用来在Web中定义图形的，是W3C推荐的。

  1. rect 矩形

  ```html
  <!-- 矩形 -->
      <!-- <rect width="100" height="100" style="fill:rgb(0,0,255);stroke-width:3;stroke:rgb(0,0,0);"> -->
      <!-- <rect width="100" height="100" style="fill:blue;stroke:pink;stroke-width:5;fill-opacity:0.1;stroke-opacity:0.9;"> -->
      <!-- 圆角矩形 -->
      <rect x="0" y="0" rx="10" ry="10" width="100" height="100" style="fill:red;stroke:black;stroke-width:1;opacity:0.5;">
  ```
  2. circle 圆
  ```html
    <!-- cx,cy为圆点坐标 r为半径 -->
    <circle cx="50" cy="50" r="50" stroke="lightgray" stroke-width="1" fill="red"/>
  ```  
  3. llipse 椭圆   
  ```html
  <!--
        cx: 中心点x坐标
        cy: 中心点y坐标
        rx: 水平半径
        ry: 竖直半径
      -->
      <ellipse cx="50" cy="50" rx="47" ry="30" style="fill:yellow;stroke:purple;stroke-width:2"/>
  ```  
  可以通过设置不同坐标点与半径来花式使用ellipse  

  4. line 线
  ```html
  <!-- line
      x1,y1:起始点坐标
      x2,y2:终点坐标
      -->
      <line x1="0" y1="0" x2="200" y2="200" style="stroke:rgb(255,0,0);stroke-width:2" />
  ```  
  5. polygon 多边形
  ```html
  <!-- points属性为多边形每个拐点的坐标 -->
  <polygon points="200,10 250,190 160,210" style="fill:lightgray;stroke:purple;strole-width:1;" />
  ```  
  6. polyline 折线  
  ```html
  <p><svg width="500" height="180">
      <polyline points="0,40 40,40 40,80 80,80 80,120 120,120 120,160" style="fill:white;stroke:red;stroke-width:4;" />
    </svg></p>
  ```  
  7. path 路径

  |命令|作用|
  |: -- :|:|
  |M|moveto 移动到起点|
  |L|lineto 连接|
  |H|horizontal lineto|
  |V|vertical lineto|
  |C|cureto|
  |S|smooth curveto|
  |Q|quadratic Bezier curve|
  |T|smooth quadratic Bezier curveto|
  |A|elliptical Arc|
  |Z|closepath|  

  ```html
    <path d="M150 0 L75 200 L225 200 Z" />
  ```  
  8. text 文字
  ```html
  <!--
    可以使用tranform属性来旋转文字
    text可以被tspan标签环绕 包含格式和位置
  -->
  <text x="0" y="15" fill="red">Draw Text in SVG</text>
  ```  
  9. Stoke属性
  * stroke 定义了颜色
  * stroke-width 定义了线的高度
  * stroke-linecap 定义了两端形状 (butt、round、square)
  * stroke-dasharray 用来创造虚线

  10. filter 滤镜 -- （清醒了再搞）

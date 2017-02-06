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
      <dt>Coffee</dt>
      <dd>- black hot drink</dd>
      <dt>Milk</dt>
      <dd>- white cold drink</dd>
    </dl>
```
>列表可以嵌套列表，可以通过自定义style来处理

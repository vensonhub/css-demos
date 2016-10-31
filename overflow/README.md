#OVERFLOW Demos

> overflow基本属性：

* visible(默认) 超出不隐藏
* hidden 超出隐藏
* scroll 有滚动条
* auto 智能一些
* inherit IE8+

> overflow-x和overflow-y(IE8+)

* overflow-x:hidden 水平被隐藏，如果overflow-x和overflow-y值不同，其中的一个值被赋值为visible，而另外一个值被赋值为hidden，scroll，或auto。visible会被重置为auto.
* overflow-y:hidden

> 兼容性

* 每个滚动条都不相同
* 宽度设定机制 （IE7 和 IE8+ 就会不同原因可能宽度设置100%）

> 作用的前提

* 非display:inline水平
* 对应方位的尺寸限制：width/height/max-width/max-height/absolute拉伸
* 对于单元格td等，还需要table为table-layout:fixed才行

> 滚动条出现的条件

* overflow:auto/overflow:scroll
* 内容的尺寸超出容器的尺寸

> body/html与滚动条

* 无论什么浏览器，默认滚动条均来自<html>，而不是<body>
* IE7浏览器默认：html{overflow:scroll;}
* IE8+浏览器默认:html{overflow:auto;}
所以想要去除页面默认滚动 html{overflow:hidden;}

> body/html与滚动条－JS与滚动高度

* Chrome浏览器是：document.body.scrollTop;
* 其他浏览器是：document.documentElement.scrollTop;
* 目前两者不会同时存在，因此，通用写法为：

```
var st = document.body.scrollTop + document.documentElement.scrollTop;
```
建议使用下面的：

```
var st = document.documentElement.scrollTop || document.body.scrollTop;
```

> overflow会有padding缺失的情况

> 滚动条的宽度

* 滚动条的宽度和高度占用页面的宽度和高度
* 准确说法应该是滚动栏的宽度。下面方法可以简单获得：



```
.box {widht:400px;overflow:scroll;}
.in {*zoom:1;/* for IE7 */}

```
```
<div class="box">
	<div id="in" class="in"></div>
</div>

console.log(400 - document.getElementById("in").clientWidth);

```
结果:IE7+/chrome/firefox 均是17px

> overflow:auto布局的潜在隐患

* 滚动条会占用容器的尺寸

> overflow 水平居中引起的跳动问题

* .container{width:1150px;margin:0 auto},因为滚动条会占用宽度，margin的auto就会减少，所以出现了跳动；

> 水平居中跳动问题的修复

* html{overflow-y:scroll}
* .container{padding-left:calc(100vw-100%);},100vw是浏览器的宽度，100%是可用宽度；

> 自定义滚动条－webkit

* 整体部分 ::-webkit-scrollbar
* 两端按钮 ::-webkit-scrollbar-button
* 外层轨道 ::-webkit-scrollbar-track
* 内层轨道 ::-webkit-scrollbar-track-piece
* 滚动滑块 ::-webkit-scrollbar-thumb
* 边角    ::-webkit-scrollbar-corner
还有一些伪类细节

> overflow与BFC

* BFC(Block Formatting context)快级格式上下文,特性具有包裹性内部无论怎么动都不会影响外部元素；
* 触发BFC是overflow非visible可以出发
* 作用一般为清除浮动影响，避免margin穿透问题，两栏自适应布局

> BFC的属性的基本表现

* overflow:hidden; 自适应，但“溢出不可见”限制应用场景
* float + float 包裹性＋破坏性，无法自适应，块状浮动布局
* position:absolute 脱离文档流自娱自乐
* display:inline-block 包裹性，无法自适应：IE6/IE7 block水平不相识
* display:table-cell 包裹性，但天生无溢出特性，绝对宽度也能自适应。

> 两栏自适应布局

```
.cell{
	display:table-cell;width:2000px;//IE8+ BFC特性
	*display:inline-block;*width:auto;//IE7- 伪BFC特性 
}
```

> overflow与绝对定位

> overflow:hidden失效

```
.overflow-hidden{
	width:300px;
	height:200px;
	border:5px solid #beceeb;
	overflow:hidden;
}

img.style.position = "absolute";
```

> overflow滚动失效

```
.overflow-auto{
	width:300px;
	height:200px;
	border:5px solid #beceeb;
	overflow:auto;
}

img.style.position = "absolute";
```

> 失效的原因

* 绝对定位元素不总是被父级overflow属性剪裁，尤其当overflow在绝对定位元素及其包含块之间的时候。包含块指：含"position:relative/absolute/fixed声明的父级元素，没有则body元素"。

```
body(包含块)
	div.overflow-hidden
		img(absolute)
```
> 如何避免失效

* overflow元素自身为包含块,比如在元素本身在加上一个position:relative
* overflow元素的子元素为包含块,div.class="overflow-hidden" > div.style="position:relative" > img.absolute
* 任意合法transform声明当作包含块,1.overflow元素自身transform;2.overflow子元素transform;

> overflow 失效妙用

```
.h0{height:0}
.ovh{overflow:hidden;}
.tr{text-align:right;}
.abs{position:absolute;}

div class="h0 ovh tr"
  &nbsp;img src="fixed-right.png" class="abs ml10 mt30"
```

> 依赖overflow的样式属性

* resize:both 水平垂直两边拉
* resize:horizontal 只有水平方向拉
* resize:vertical 只有垂直方向拉
* 但是，overflow元素不能为visible
* text-overflow:ellipsis

> overflow与锚点











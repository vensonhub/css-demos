#line-height Demos

> line-height的定义

* line-height 行高，两行文字基线之间的距离；

> line-height与行内框盒子模型

* 例如：```<p>普通文字<em>em</em>标签</p>```
* 1.内容区域，是一种围绕文字看不见的盒子。内容区域的大小与font-size有关；
* 2.内链盒子，内链盒子不会让内容块显示，而是排成一行。如果外部含inline水平标签（span，a，em等），则属于内链盒子。如果只是文字，则属于匿名内链盒子。
* 3.行框盒子，每一行就是一个行框盒子，每个行框盒子是由内链盒子组成。
* 4.p标签所在的包含盒子，此盒子由一行一行的行框盒子（line boxes）组成；

> line-height的高度机制和原理

> 文本占据的高度

```<p>普通文字<em>em</em>标签</p>```

```console.log(document.querySelector("p").clientHeight)```

p的值为：36px

p元素的高度从何而来？
是由line-height决定的；

> 需要知道的

* 行高由于继承性，影响无处不在，即使单文本也不例外；
* 行高只是幕后黑手，高度的表现不是行高，而是内容区域和行距；
* 内容区域高度＋行间距 ＝ 行高
* 内容区域高度只与字号以及字体有关，与line-height没有任何关系
* 在simsun字体下，内容区域高度等于文字大小；如下：
* 在simsun字体下，font-size + 行间距 ＝ line－height
* 行间距，如：font-size=240px;line-height=360px;，则 行间距＝360px-240px = 120px;

> line-height 各个属性值

* normal 默认属性值，跟着用户浏览器走并且是与字体相关联；
* number 根据当前的font-size来决定，line-height=1.5*20px;
* length 可以是1.5em;1.5rem;20px;20pt;
* percent 可以用百分比，相对于设置该行高属性元素的font-size,line-height=150%*20px;
* inherit 继承IE8+

> line-height 与 图片

> 行高会不会影响图片实际占用的高度？

```<p><img src="mm.jpg"></p>```
行高不会影响图片实际占据的高度；

> 消除图片底部间隙的方法

* 图片块状化 img{display:block;}
* 图片底线对齐 img{vertical-align:bottom;}
* 行高足够小－基线位置上移 .box{line-height:0;}

> 行高的实际应用

* 大小不固定的图片、多行文字垂直居中；

```
图片水平垂直居中，IE8+
.box {line-height:300px;text-align:center;}
.box > img{vertical-align:middle;}
```

```
多行文本水平垂直居中
.box{line-height:250px;text-align:center;}
.box > .text{display:inline-block;line-height:normal;text-align:left;
vertical:middle;max-width:100%;}
```

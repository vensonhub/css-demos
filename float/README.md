#Float
> 1、Float设计初衷是什么？

浮动设计的初衷是解决文字环绕效果.

> 2、Float包裹和破坏。

> 包裹性：

1. 收缩
2. 坚挺
3. 隔离
	
> 除了float同时具有包裹性的还有以下元素：

* display:inline-block/table-cell/...
* position:absolute/fixed/sticky
* overflow:hidden/scroll

> 破坏性：

> 具有破坏性的出了float，还有：

* display:none
* position:absolute/fixed/sticky

> 清除浮动所带来的影响

* 方法1:在底部插入clear:both
* 方法2:父元素BFC(IE8+)或者haslayout(IE6/IE7)
> BFC/haslayout通常声明:

* float:left:right
* position:absolute/fixed
* overflow:hidden/scroll(IE7+)
* display:inline-block/table-cell(IE8+)
* width/height/```zoom:1```/...(IE6/IE7)
> 权衡后的策略

```
IE8+或其他浏览器
.clearfix:after{
	content:'';
	display:block;
	height:0;
	overflow:hidden;
	clear:both;
}
IE6/IE7
.clearfix{
	*zoom:1;
}
或者
.clearfix:after{
	content:'';
	display:table;
	clear:both;
}
.clearfix{
	*zoom:1;
}
```

浮动可以让元素block化
> 浮动与流体布局

> 文字环绕衍生－单侧固定

> 浮动与兼容

* 
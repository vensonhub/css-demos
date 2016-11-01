#Vertical-align Demos

> 基本属性和组成

* inherit
* 线类 包括：baseline,top,middle,bottom
* 文本类 包括:text-top,text-bottom
* 上标下标类 包括:sub,super
* 数值百分比类 包括:20px,2em,20%...
* ie6/ie7下vertical-align百分比值不支持小数line-height
* vertical-align和line-height是好基友。。。

> vertical-align 起作用的前提

* inline 和 table-cell 时起作用
* inline:img,span,strong,em,自定义元素
* inline-block:input,button
* table-cell:td
* 默认情况下图片，按钮，单元格生效

> vertical-align与line-height

* vertical-align百分比是相对于line－height值计算的

```
{
	line-height:30px;
	vertical-align:-10%;
}

{
	line-height:30px;
	vertical-align:(-3px);/* 30px * -10%= -3px*/
}
```

* vertical-align图片的一些问题处理方式：
* 原因因为vartical-align是基于基线对其的如字母（像英文字母本一样可能会写到线下面）
* 所以可以用display:block或者vertical-align:middle,top,bottom等
* 大小图片不固定的近似垂直居中:vertical-align:middle;line-height:30px;
* text-align:justify任意数目列表的两端对齐效果：

```
justify-fix{display:inline-block;widht:250px}

p style="text-align:justify;"
	img src="mm.png" widht="250px"
	img src="mm.png" widht="250px"
	img src="mm.png" widht="250px"
	img src="mm.png" widht="250px"
	i class="justify-fix" /*占位标签*/
	i class="justify-fix"
	i class="justify-fix"
	
```

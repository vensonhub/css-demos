#z-index Demos

> z-index 基础

* z-index:auto;
* z-index:integer;
* z-index:inherit;
* 支持负值；
* 支持css animation动画；
* 在css2.1时代，需要和定位配合使用；

> z-index与定位属性

* position:static;z-index:2(不生效);
* position:relative;z-index:2(生效);
* position:absolute;z-index:2(生效);
* position:fixed;z-index:2(生效);
* position:sticky;z-index:2(生效);

> 如果定位元素z-index没有发生嵌套

* 后来居上的准则；
* 哪个大；哪个上；

> 如果定位元素发生嵌套

* 祖先优先原则；

> css中的层叠上下文和层叠水平

* 层叠上下文表示在z轴的顺序
* 用户 当官层叠上下文 家族嵌套
* 哪些元素具有成叠上下文：页面的根元素天生具有层叠上下文，称之为“根层叠上下文”；z-index值为数值的定位元素也具有层叠上下文；其他属性......
* 层叠水平：层叠水平上下文的每一个元素都有一个层叠水平，决定了同一个层叠上下文中元素在z轴上的显示顺序；
* 层叠上下文可以嵌套，组合成一个分层次的层叠上下问；
* 每个层叠上下文和兄弟元素独立；当进行层叠变化渲染的时候，只需要考虑后代元素；
* 每个层叠上下文自成体系的，当元素内容被层叠后，整个元素被认为是在父层的层叠顺序中；

> 层叠顺序

* 层叠顺序表示元素发生层叠时候有特定的垂直显示顺序；

> z-index与层叠上下文

* 定位元素默认z-index:auto可以看成z-index:0;
* z-index不为auto的定位元素会创建层叠上下文；
* z-index层叠顺序的比较止步于父级层叠上下文;

> 其他参与层叠上下文的属性

* z-index值不为auto的flex项（父元素display:flex|inline-flex）
* 元素的opactiy值不是1
* 元素的transform值不为none
* 元素mix-blend-mode值不是normal
* 元素filter值不是none
* 元素isolation值是isolate
* fixed声明
* will-change指定的属性值为上面任意一个
* 元素的-webkit-overflow-scrolling设为touch

> 非定位元素与z-index

* 非依赖z-index的元素他的级别是z-index:auto级别；






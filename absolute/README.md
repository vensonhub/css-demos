#absolute

> absolute和float相似也同样具有包裹性和破坏性；
> absolute无依赖限制

* 不受relative限制的absolute定位，行为表现上是不使用top/right/bottom/left任何一个属性或使用auto作为值.

> 定位的行为表现

1. 脱离文档流
2. 脱离文档流后，还在原来的位置。

> absolute与去浮动

* 绝对定位生效时，浮动一定是失效的；
* absolute与位置跟随

> z-index 无依赖
* 如果只有一个绝对定位元素，自然不需要z-index，自动覆盖普通元素；
* 如果两个绝对定位，控制DOM流的前后顺序达到要覆盖的效果，依然无z-index;
* 如果多个绝对定位交错，非常少见，z-index控制：1就可以了；
* 如果非弹窗类绝对元素定位,z-index>2,必定z-index冗余了；

> 宽度高度可以与top/right/bottom/left互相代替
width:100%,height:100%;
等同
top:0,right:0,bottom:0,left:0;
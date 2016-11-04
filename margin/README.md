#margin Demos

> margin与容器尺寸

* 可视尺寸－clientWidth
* 占据尺寸－outerWidth

> margin与可视尺寸

* 适用于没有设定width/height的普通block元素，float元素absolute/fixed元素inline水平table-cell元素都不可以
* 只适用水平方向尺寸

> margin与占据尺寸

* block/inline-block水平元素均适用
* 与有没有设定width/height值无关
* 适用水平方向和垂直方向

> margin与百分比单位

* 普通元素的百分比margin都是相对于容器的宽度计算
* 绝对定位元素的百分比margin是相对于第一个定位祖先元素（relative/absolute/fixed）的宽度计算的！

> margin与重叠

* margin只发生在block水平元素上（不包括float和absolute）
* 不考虑writing-mode,只发生在垂直方向(margin-top/margin-bottom)
* 相邻的兄弟元素会发生重叠
* 父子元素会发生重叠（第一个和最后一个元素）
* 空的block

> 父子margin重叠其他条件

> margin-top重叠

* 父元素非块状格式化上下文元素
* 父元素没有border-top设置
* 父元素没有padding-top值
* 父元素和第一个子元素之间没有inline元素分隔

> margin-bottom重叠

* 父元素非块状格式化上下文元素
* 父元素没有border-bottom设置
* 父元素没有padding-bottom设置
* 父元素和最后一个子元素之间没有inline元素分隔
* 父元素没有height,min-height,max-height限制

> 空block元素margin重叠其他条件

* 元素没有设置border
* 元素没有padding设置
* 里面没有inline
* 没有height,或者min-height

> 重叠计算规则

* 正正取大值
* 正负值相加
* 负负最负值

> margin的auto

* 分配剩余空间

> margin 负值

* margin负值下的两端对齐

> margin 无效情况

* inline元素的垂直是无效的，前提非替换元素，例如：不是img元素；正常书写模式；
* margin重叠
* display:table-cell与margin,应用于除了display:table相关类型（不包括table-cpation,table以及inline-table）的所有。甚至也可以应用::first-letter
* position:absolute与margin，绝对定位元素非定位方向"无效"；

> margin-start和margin-end

* 正常的流向，margin-start等同于margin-left,两者重叠不累加;
* 如果水平流是从右往左，margin-start等同于margin-right;
* 在垂直流下(writing-mode:vertical-*;)等同于margin-top;
* margin-collapse margin重叠可以用此属性，属性分别为-webkit-margin-collapse:collapse(默认－重叠)|discard(取消)|separate(分隔)
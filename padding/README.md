#padding Demos
> padding与容器尺寸的关系

* 对于block水平元素，加了padding后会增加元素的尺寸；
* 如果box-sizing:border-box;在加入padding后此时的padding是不会影响宽度尺寸的，但是，一旦padding设置过大还是会影响宽度尺寸的；
* width非auto，padding影响尺寸；
* 对于inline水平元素，水平padding影响尺寸，垂直padding不影响尺寸，但是会影响背景色区域（占据空间会变大,clientHeight,scrollHeight都会变大）

> padding负值

* padding不支持负值

> padding百分比值

* padding百分比按照宽度计算

> inline元素的padding

* 同样相对于宽度计算
* 默认高度宽度细节有差异
* padding会断航
* inline元素的垂直有padding会让幽灵空白节点出现，也是规范中的strut。设置font-size=0让其看不见；

> 标签元素的内置padding

* ol/ul列表 默认有padding-left,单位是px；
* 所有浏览器input/textarea输入框内置padding；
* 所有浏览器button按钮内置padding;
* 部分浏览器select下拉内置padding,如firefox ie8+可以设置padding；
* 所有浏览器radio/checkbox单选框无内置padding；
* button按钮元素的padding最难控制；

> padding与图形绘制

> padding布局

* 适用百分比勾结固定比例的结构
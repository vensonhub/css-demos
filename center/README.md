#各种居中方式

> 把margin设为auto

具体说就是把药居中的元素的margin-left和margin-right都设为auto，此方法职能进行水平居中，且对浮动元素或绝对定位元素无效。

> 使用text-align:center

只能对图片，按钮，文字等行内元素(display:inline/inline-block等)进行水平居中。但是，ie6和ie7这两个浏览器中，它可以对任何元素水平居中的；呃。。。

> 使用line-height让单行文字垂直居中

把文字的line-height设为文字的父容器，适用于只有一行的文字情况;

> 使用line-height让多行文本水平垂直居中

.box{line-height:200px;text-align:center;}
.box>text{display:inline-block;line-height:normal;vertical-algin:middle;max-width:100%;}
因为父级把line-height设置了200px因为line-height有继承性的原因,故需要把line-height设置为normal；

> 使用line-height让大小不固定的图片居中

.box{line-height:300px;text-align:center;}
.box > img{vertical-align:middle;}
图片其实是按照baseline对齐的



> 使用display:table-cell居中

不是单元格的元素可以用table-cell来模拟一个单元格，这样就有了居中特性了；

> 使用绝对定位来进行居中

此方法只适合那些已经知道宽度或高度的元素；绝对定位进行居中的原理是通过把这个绝对定位元素的left或top的属性设为50%,这个时候元素并不是居中的，而是逼居中的位置向右或向左偏了这个元素宽度或高度的一半距离，所以要使用一个负margin-left或margin-top值来把它拉回到居中的位置，这个负的margin值就是这个元素的宽度或高度的一半。

另一种就是将top,left,right,bottom设置为0，此时就相当于width:100%;height:100%;这个时候如果在使用margin:auto;就可以进行居中定位了；

> 使用浮动配合相对定位来进行水平居中

浮动居中的原理是把浮动元素相对定位到父元素宽度50%的地方，但这个时候元素还不是居中的，而是比居中的那个位置多出了自身一半的宽度，这时就需要它里面的子元素在用一个相对定位，把那多出的自身一半的宽度拉回来，而因为相对定位正是相对于自身来定位的，所以自身一半的宽度只要把left或right设为50%就可以得到了，因而不用知道自身的实际宽度是多少。
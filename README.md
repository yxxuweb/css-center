# css 居中

## 水平居中

1. 行内元素

我们可以通过对其父级块元素做如下处理来使行内元素居中。适用于inline,inline-block,inline-table,inline-flex等。

> 看 index-1.html。

2. 块级元素

我们可以通过将一个块级元素的margin-left和margin-right同时设置为auto来使其居中。（注意：此时元素必须定义有width，否则将填满宽度，谈不上水平居中。）通常由以下简写来定义：

> 看 index-2.html

3. 多个块级元素

当同一行中有两个或以上块级元素需要居中时，我们不得不通过改变display的类型来实现。下面的例子分别将display设置为inline-block以及flexbox的例子

> 看 index-3.html

当你指的是多个位于同一列上的块级元素时，将margin设为auto的技术依旧生效

> 看 index-4.html

## 垂直居中

1. 行内元素

***单行***

有时行内元素或文本能够做到垂直居中，仅仅是因为元素上、下的padding相等。

> 看 index-5.html

在某些情况当padding不适用，并且文字不会换行时，有一个技巧：当line-height与height相等时，文字垂直居中。

> 看 index-6.html

***多行***

上下padding相等依旧可以解决这个问题。但当此方法不生效时，可能是元素或文本处于table cell中，要么是html语义中的table，要么是CSS中的设置。这种情况下，我们使用vertical-align来完成垂直居中。注意：此为特殊用法，vertical-align平时用来处理一行中的元素如何排列

> 看 index-7.html

如果类似table的那些无效时，也许我们应该尝试下flexbox。 在flex中，一个子元素可以轻易地在父元素中居中。
记住，这种做法仅在腹肌元素高度固定时(px, %等)才有效。

> 看 index-8.html

如果上述两种做法都无效，那么我们可以采用“幽灵元素”技术。在这种做法中，一个伪元素占据父元素的全部高度，然后文本在其中垂直居中。

> 看 index-9.html

## 块级元素

1. 高度已知

当我们知道高度时，可以按照如下方法实现垂直居中：

> 看 index-10.html

2. 高度未知时

在这种情况下，我们仍然可以实现垂直居中：将元素下移父级元素的50%，再上移自身高度的50%。

> 看 index-11.html

3. 可以使用flexbox时

> 看 index-12.html


## 同时垂直居中，水平居中。完美居中的三种情况

### 元素宽高固定时

此时可以使用绝对定位将元素置于父元素(50%，50%)的位置，之后再通过将margin设置为负值。这种方法拥有广泛的浏览器支持

> 看 index-13.html

### 元素宽高不固定时

当宽高不固定时，我们可以使用transform属性来实现将元素在两个方向同时移动50%。该宽度基于当前元素的宽度。

> 看 index-14.html

### 可以使用flexbox时

> 看 index-15.html

### 补充额外一种兼容性很好的方法

```css
.Absolute-Center {
  margin: auto;
  position: absolute;
  top: 0; left: 0; bottom: 0; right: 0;
}
```

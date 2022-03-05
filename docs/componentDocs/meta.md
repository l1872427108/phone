# meta视口

meta 视口的目的就是让布局视口和理想视口尺寸匹配。

### 值
1. width: 设置布局视口的宽度和特定的值。
width 是用来改变布局视口的。可以设置为具体的值 width=400
2. init-scale: 设置页面初始缩放程度和布局视口的宽度。
初始缩放程度。1代表100%，2代表200%。缩放程度根据理想视口计算的。
initial-scale=1视觉视口尺寸和理想视口的尺寸一样。
initial-scale=2视觉视口的宽度是理想视口的一半。
3. minimum-scale: 最小缩放程度.
4. maximum-scale: 最大缩放程度
5. user-scaleable: 阻止用户缩放。


### 完美视口
设置 initial-scale=1 时，理想视口的尺寸会随着屏幕的旋转变换。布局视口是 320px。就解决了safairi 不能转屏的一个问题。

IE 中 initial-scale=1 时它在横屏模式下宽320px，但是 width=device-width时它会从320变为480px。 为了兼容苹果和IE。引出了完美视口。
```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```
解决了 Safari 和 IE 的问题。布局视口在设备旋转的时候作出响应。


### 太大的元素
overflow： visible； 会使得太大的元素超出去。

使用 width=device-width 或 initial-scale=1中的一个，不同时使用两个. 有些浏览器会扩展布局视口的宽度来容纳这个元素。

如果使用两个，大部分浏览器都不会改变布局视口。因为我们更应该使用 meta视口。

### 布局视口的最小宽度。
```html
<meta name="viewport" content="width=400,initial-scale=1">
```
布局视口的宽度设置为400， 然后我们再把它设置为理想视口的宽度。
会先选每个方向最大的尺寸。因此早起的 iphone 两侧都是最大的。


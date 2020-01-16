# SVG

## 一. 基本用法

直接在HTML嵌入svg代码,svg相当于是一个画布,画布内部可以画一些图案,坐标是以左上角为原点,左边是x轴,下边是y轴。

```
<svg version="1.1">
   <circle cx="100" cy="50" r="40" stroke="black" stroke-width="2" fill="red" />
</svg>
```

## 二. 用svg绘制各种图形

### 矩形

```
<svg version="1.1">
  <rect width="300" height="100"
  style="fill:rgb(0,0,255);stroke-width:1;stroke:rgb(0,0,0)"/>
</svg>
```

## 圆形

cx表示圆心距离x轴的距离,cy表示y轴的距离,r表示圆的半径,stroke表示画笔的颜色,stroke-width表示画笔的宽度,不算在半径内,fill表示填充的颜色。
```
<svg version="1.1">
  <circle cx="100" cy="50" r="40" stroke="black"
  stroke-width="2" fill="red"/>
</svg>
```

## 椭圆
椭圆和原型类似。
```
<svg version="1.1">
  <ellipse cx="300" cy="80" rx="100" ry="50"
  style="fill:yellow;stroke:purple;stroke-width:2"/>
</svg>
```

## 直线
x1、y1为起始点坐标,x2、y2为终点坐标。
```
<svg version="1.1">
  <line x1="0" y1="0" x2="200" y2="200"
  style="stroke:rgb(255,0,0);stroke-width:2"/>
</svg>
```

## 多边形
points 属性定义多边形每个角的 x 和 y 坐标。每个点是按照顺序连接。
```
<svg  height="210" width="500">
  <polygon points="200,10 250,190 160,210"
  style="fill:lime;stroke:purple;stroke-width:1"/>
</svg>
```

## 曲线
曲线和多边形类似，没有最后一笔封路。
```
<svg version="1.1">
  <polyline points="20,20 40,25 60,40 80,120 120,140 200,180"
  style="fill:none;stroke:black;stroke-width:3" />
</svg>
```

## 路径

路径中 d是最复杂的属性，path也是可以画各种图形的一个标签了。

```
<svg xmlns="http://www.w3.org/2000/svg" version="1.1">
    <path d="M150 0 L75 200 L225 200 Z" />
</svg>
```

### path 属性中 d 的取值



#### 1. M 
参数：x,y
描述：moveto，移动到。移动虚拟画笔到指定的（x,y）坐标，仅移动不绘制。

#### 2. m 
参数：x,y
描述：同M，但使用相对坐标。

#### 3. L 
参数：x,y
描述：lineto，连直线到。从当前画笔所在位置绘制一条直线到指定的（x,y）坐标。

#### 4. l 
参数：x,y
描述：lineto，连直线到。同L，但使用相对坐标。

#### 5. H，h
参数：x
描述：绘制一条水平直线到参数指定的x坐标点，y坐标为画笔的y坐标。

#### 6. V，v
参数：y
描述：从当前位置绘制一条垂直直线到参数指定的y坐标。

#### 7. C，c
参数：x1,y1 x2,y2 x,y
描述：三次方贝塞尔曲线。从当前画笔位置绘制一条三次贝兹曲线到参数（x,y）指定的坐标。x1，y1和x2,y2是曲线的开始和结束控制点，用于控制曲线的弧度。

#### 8. S，s
参数：x2,y2 x,y
描述：平滑三次方贝塞尔曲线,从当前画笔位置绘制一条三次贝塞尔曲线到参数（x,y）指定的坐标。x2,y2是结束控制点。开始控制点和前一条曲线的结束控制点相同。

#### 9. Q，q
参数：x1,y1 x,y
描述：二次方贝塞尔曲线。从当前画笔位置绘制一条二次方贝塞尔曲线到参数（x,y）指定的坐标。x1,y1是控制点，用于控制曲线的弧度。

图片展示：https://img-blog.csdn.net/20160712175603053?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center

#### 10. T，t
参数：x,y
描述：平滑的二次贝塞尔曲线。从当前画笔位置绘制一条二次贝塞尔曲线到参数（x,y）指定的坐标。控制点被假定为最后一次使用的控制点。

#### 11. A，a
参数：rx,ry x-axis-rotation large-arc-flag,sweepflag x,y
描述：椭圆弧线。从当前画笔位置开始绘制一条椭圆弧线到（x,y）指定的坐标。rx和ry分别为椭圆弧线水平和垂直方向上的半径。x-axis-rotation指定弧线绕x轴旋转的度数。它只在rx和ry的值不相同是有效果。large-arc-flag是大弧标志位，取值0或1，用于决定绘制大弧还是小弧。sweep-flag用于决定弧线绘制的方向。

#### 12. Z
描述：闭合。


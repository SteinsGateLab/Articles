#CSS3之3D
最近想要重构一下自己的个人网站，就想起CSS3的3D效果。之前没有很清晰的去学习。这次趁着有重构的想法，就去学习并总结了一下。

##CSS3的动画功能
- transition
实现平滑过渡
- animation
利用关键帧

在这里先总结transition，animation相对复杂一些，之后再作一次总结。

##transition
```
transition：<property> <duration> <mode>
or:
transition-property:<property>
transition-duration:<duration>
transition-timing-function:ease || linear || ease-in || ease-out || ease-in-out
```
兼容
- transition
- -webkit-transition
- -moz-transition
- -o-transition
- -ms-transition

## 3D
### Key Properties
- perspective
- perspective-origin
浏览器是三维世界的窗口，三维物体与窗口的距离就是perspective属性的值。从窗口看世界的视点就是perspective-origin，这个值一般设置的是两个百分比数值，分别对应x轴和y轴的位置。
这两个属性的设置告诉浏览器我们将怎样看里面的三维世界。这就完成了三维设置的工作。
### Property : transform
利用transform调整元素展现三维效果。
正方向：X向右，Y向下，Z从屏幕向人
transform-style:preserve-3d
translate——
    translateX(x px)
    translateY(y px)
    translateZ(z px)
rotate——
    rotateX(x deg)
    rotateY(y deg)
    rotateZ(z deg)
transform-origin调整旋转中心，默认是正中心。
 X轴  | Y轴  | Z轴 
------|------|------
left  |top   |length px
center|center|
right |bottom|

#### 最后
三维效果还是很难的，砖瓦有了，想要建起大楼还是要有自己的设计蓝图+搬砖^_^。

2016-05-27
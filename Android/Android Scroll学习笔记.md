# Android Scroll 学习笔记
本文是笔者学习《Android群英传》一书第五章的一些心得笔记。
## 滑动效果是如何产生的
View的滑动本质上就是View的移动，即改变View的位置。原理是不断改变View的坐标。为了实现这个效果，就必须不断监听用户的触摸事件，根据坐标动态地改变View的位置，从而实现滑动效果。那么首先就要了解一下Android中的坐标和触摸事件的相关知识。
### Android中的坐标系
 - 绝对坐标系  
	- 屏幕左上角的顶点为原点
	- getLocationOnScreen(int location[])
	- getRawX() getRawY()	
 - 视图坐标系
	- 父视图左上角的顶点为原点
	- getX() getY()
 - 两种坐标系的共同点
 	- 从顶点出发，向右为x轴正方向，向下为y轴正方向

### 触控事件MotionEvent
通常在onTouchEvent(MotionEvent event)方法中通过event.getAction()方法获取触控事件类型，然后根据不同的类型进行不同的操作。

### 获取坐标和距离的API
 - View提供的获取坐标方法（需要注意获取的都是相对于父布局的**顶边和左边**的距离）
	- getTop() 获取View自身顶边到父布局**顶边**的距离
	- getLeft() 获取View自身左边到父布局**左边**的距离
	- getBottom() 获取View自身底边到父布局**顶边**的距离
	- getRight() 获取View自身右边到父布局**左边**的距离
 - MotionEvent提供的方法
	- getX() 获取点击事件距离**控件左边**的距离，即**视图坐标**
	- getY() 获取点击事件距离**控件顶边**的距离，即**视图坐标**
	- getRawX() 获取点击事件距离**屏幕左边**的距离，即**绝对坐标**
	- getRawY() 获取点击事件距离**屏幕顶边**的距离，即**绝对坐标**
## 实现滑动的七种方法
1. Layout方法
2. offsetLeftAndRight() 和 offsetTopAndBottom()
3. LayoutParams（**书中的给出方法有BUG，因为自定义view不一定位于父布局的1号位，所以不能单纯通过调整view的margin来调整位置。必须在自定义view外单独套一层layout才能确保正确运行**）
4. scrollTo 和scrollBy （**注意此方法移动的是“画框”，所以“画布”的位移与偏移量相反。而且，如果view不是parent中唯一的view，其他view也会受到影响**）
5. Scroller （此方法可以实现平滑移动而非瞬间移动。ViewDragHelper也是通过这种方法实现的）
6. 属性动画
7. ViewDragHelper
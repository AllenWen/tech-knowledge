### 流式布局实现方式

* 自定义ViewGroup(FlowLayout)
* 官方FlexboxLayout
* 官方ChipGroups + Chips
* 官方RecyclerView + FlexboxLayoutManager
* 官方RecyclerView + GridLayoutManager + Span
* 官方ConstraintLayout + Flow

### ConstraintLayout隐藏科技

* GuideLine, 辅助线
* Barrier, 隔离线
* Group, 多个控件同时隐藏或者显示
* Placeholder, 占位
* Flow, 流式布局
* Layer, 层布局
* ImageFilterButton和ImageFilterView, 圆角，层叠图片，色温，亮度等
* MockView, 演示
* ConstraintProperties, 流式api修改熟悉
* **[MotionLayout](https://blog.csdn.net/knight1996/article/details/108015536)**

### 实现图片圆角方式

* CardView
* ImageFilterView
* ViewOutlineProvider
* RoundedBitmapDrawable
* ShapeableImageView, 建议
* 自定义view + ClipPath, 有背景问题
* 自定义view + BitmapShader
* 自定义view + PorterDuffXfermode
* 三方库如Glide等

### 沉浸式状态栏

* 状态栏

| 版本       | 透明状态栏  | API                                                                                                                                                                                                                                                       |
|----------|--------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| &lt;4.4  | ❌      | `activity.getWindow().addFlags(WindowManager.LayoutParams.FLAG_TRANSLUCENT_STATUS); `                                                                                                                                                                     |
| 4.4-5.0  | ✅(带渐变) | `getWindow().addFlags(WindowManager.LayoutParams.FLAG_DRAWS_SYSTEM_BAR_BACKGROUNDS); getWindow().clearFlags(WindowManager.LayoutParams.FLAG_TRANSLUCENT_STATUS); getWindow().setStatusBarColor(getResources().getColor(android.R.color.holo_red_light));` |
| &gt;=5.0 | ✅      | `同上`                                                                                                                                                                                                                                                      |

* 字体状态栏

| 版本    | 黑白字体状态栏 |
|-------|---------|
| <6.0  | ❌       |
| >=6.0 | ✅       |

* 设置字体状态栏
  `getWindow().getDecorView().setSystemUiVisibility(
  View.SYSTEM_UI_FLAG_LAYOUT_FULLSCREEN|View.SYSTEM_UI_FLAG_LIGHT_STATUS_BAR);`

* 附：[刘海屏适配](https://www.jianshu.com/p/7a934313637e)

### Fragment切换页面RecyclerView自动滚动问题

* 本质是RecyclerView的focusableInTouchMode默认为true抢占焦点导致，需更改父组件设置，两种方式：

1. `android:focusable="true"
   android:focusableInTouchMode="true"`
2. `android:descendantFocusability="blocksDescendants"`

### 自定义View

* [自定义View系列](https://github.com/GcsSloop/AndroidNote/blob/master/CustomView/README.md)

### CoordinatorLayout相关问题

* [android CoordinatorLayout使用](https://blog.csdn.net/xyz_lmn/article/details/48055919)
* [CoordinatorLayout 完全解析](https://www.jianshu.com/p/4a77ae4cd82f)
* [CoordinatorLayout嵌套CoordinatorLayout的滑动处理](https://stackoverflow.com/questions/34181372/coordinatorlayout-inside-another-coordinatorlayout)
* [解决CoordinateLayout+AppbarLayout+TabLayout+Viewpager不能滑动问题](https://blog.csdn.net/qq_41056581/article/details/80929807)
* [自定义Behavior防抖动](https://github.com/yangchong211/YCBlogs/blob/master/android/08.%E5%A4%8D%E6%9D%82%E6%8E%A7%E4%BB%B6/02.%E8%87%AA%E5%AE%9A%E4%B9%89Behavior%E9%98%B2%E6%8A%96%E5%8A%A8.md)

### NestedScroll嵌套滚动

* [ViewPager in a NestedScrollView](https://stackoverflow.com/questions/30580954/viewpager-in-a-nestedscrollview#comment55993323_33385207)
* [Android嵌套滚动(NestedScrolling)总结](https://blog.csdn.net/etwge/article/details/88689921)

### 滚动选择器PickerView

* [滚动选择器PickerView](https://blog.csdn.net/zhongkejingwang/article/details/38513301)
# 移动端H5画面制作新年贺卡（CSS3实现动画效果）
web浏览请切换手机浏览模式[戳我在线浏览](https://yangpeijia.github.io/H5-happynewyear/)

手机扫下面二维码可预览

![二维码](https://github.com/yangpeijia/H5-happynewyear/blob/master/%E4%BA%8C%E7%BB%B4%E7%A0%81.jpg)

模仿慕课网相关课程制作，虽然只有三页，但用到了不少技能，自己也添加了一些功能上去。

功能包括音乐播放与控制、灯笼闪烁、图标自动旋转、春联浮现动画、页面自动播放，页面切换转场效果（淡入淡出）、手指滑动切换页面等。

字体用的是图片，因为引入字体的文件至少需要3M，对于移动端加载来说太庞大。

大部分功能主要用animation+@keyframe+transform属性实现。

由于需要自适应移动端，这里主要以vh和vw为单位设置元素宽高。

自己在这个课程的基础上添加了春联浮现动画、手指滑动切换页面的功能。

浮现功能通过控制opacity+scale来实现。
手指滑动切换页面的功能会比较复杂，这里通过监听每一个页面的touchstart和touchend事件，控制每个页面的display属性。

这个过程中由于课程的自动播放是通过监听page1触摸事件来实现，为了不与手指滑动切换页面事件一起发生，所以我改为通过绑定灯笼的click事件触发自动播放，
虽然会有300ms的延迟，但是这个页面的交互效果没有那么复杂，对反应时间要求没有那么严格，所以这个选择性价比最高。

如果自动播放完H5再用触摸滑动返回上一页，由于自动播放时page2添加了一个fadeOut效果，切换页面时会变成空白，所以需要先移除fadeOut效果，在js脚本中，
我在切换页面时统一移除了fadeOut效果，解决了这个问题。


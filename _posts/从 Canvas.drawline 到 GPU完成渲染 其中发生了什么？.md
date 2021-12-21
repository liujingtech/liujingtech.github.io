 # 从 Canvas.drawline 到 GPU完成渲染 其中发生了什么？
我们在移动端开发的日常工作中，对调用canvas进行绘制应该不陌生，但可能对在调用后具体发生了什么感到好奇。这次打算深入浅出的聊一下这个流程，整篇分为两个部分，一个是application的部分，另一个是在它之后交给GPU渲染管道的部分。
![](source/img/2021-11-04-17-03-53.png)

可以看见渲染对象经由 Flutter / iOS / Android 等上层应用处理成数据，再交给几何处理获得几何图形后，栅格化将这些图形做叠加转换等处理，最后输出成像素点交给显示器。


我们可以在分开仔细讲一讲这几个阶段

Application 
上层应用通常在展示 UI 后，经过用户触摸动作（点击，拖拽，旋转等），需要进一步更新 UI。
比如：在 Android 中，通过对 xml 文件的解析器进行拆分，并且获得布局控件的颜色大小位置等属性。
 ![](source/img/2021-11-05-17-34-27.png)

## 参考资料
1. Android Graphics Pipeline ：从Button到Framebuffer https://blog.csdn.net/xiaosongluo/article/details/45070749
2. 
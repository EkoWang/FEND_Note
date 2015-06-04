<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Photoshop](#photoshop)
  - [工具, 面板, 视图](#%E5%B7%A5%E5%85%B7-%E9%9D%A2%E6%9D%BF-%E8%A7%86%E5%9B%BE)
  - [测量及取色](#%E6%B5%8B%E9%87%8F%E5%8F%8A%E5%8F%96%E8%89%B2)
  - [切图](#%E5%88%87%E5%9B%BE)
  - [保存](#%E4%BF%9D%E5%AD%98)
    - [保存格式的选择](#%E4%BF%9D%E5%AD%98%E6%A0%BC%E5%BC%8F%E7%9A%84%E9%80%89%E6%8B%A9)
  - [图片修改与维护](#%E5%9B%BE%E7%89%87%E4%BF%AE%E6%94%B9%E4%B8%8E%E7%BB%B4%E6%8A%A4)
  - [图片优化与合并](#%E5%9B%BE%E7%89%87%E4%BC%98%E5%8C%96%E4%B8%8E%E5%90%88%E5%B9%B6)
    - [图片的兼容](#%E5%9B%BE%E7%89%87%E7%9A%84%E5%85%BC%E5%AE%B9)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Photoshop

**切图** 从设计稿中切除网页的素材并在代码中引入图片 (复杂的图片或者解决兼容问题)

```html
// 设计稿 (*.psd) -> 产出物 (*png, *.jpg)

<img src="../img/avatar.jpg" alt="desc">

<style type="text/css" media="screen">
  background-image: url(../../img/sprite.png);
  background-position: 0 0;
</style>
```

### 工具, 面板, 视图

在全局设置下将单位修改为像素，因其在 CSS 中运用最广。设置工作区布局为切图及图片编辑做准备（所需窗口为信息窗口，图层窗口以及历史记录窗口）。

![](../img/P/photoshop-mainWindow.png)

**切图常用工具**

|工具名|示意图|注释|
|------|:----:|----|
|移动工具| ![](../img/H/hwa_03.png)||
|矩形选框工具| ![](../img/H/hwa_01.png)||
|魔棒工具|![](../img/H/hwa_05.png)|（容差 Tolerance 越小选择的范围就越小）|
|剪裁工具| ![](../img/H/hwa_06.png) ||
|切片工具| ![](../img/H/hwa_07.png)||
|缩放工具| ![](../img/H/hwa_34.png)||
|取色器| ![](../img/H/hwa_31.png)||

图层（单层元素）与组（类似于文件夹）的区别。

**辅助视图**，在视图菜单下启动

- 对齐，会启动靠近吸附功能
- 标尺，<kbd>Command</kbd> + <kbd>R</kbd>
- 参考线，<kbd>Command</kbd> + <kbd>;</kbd>

![](../img/P/photoshop-menu.png)

NOTE: 所有工具及快捷键如下。

![](../img/T/ToolsPanelOverview.png)

### 测量及取色

所有能接受数字的属性都需要测量并尽可能百分百的还原设计稿。

- 宽度，高度 (width, height)
- 内外边距 (padding, margin)
- 边框 (border)
- 定位 (position)
- 文字大小 (font-size)
- 行高 (line-height)
- 背景位置 (background-position)

NOTE: 测量时尽可能放大画布以减少误差。量取文字是为了减少误差尽量选取尺寸大的文字进行测量。

![](../img/P/photoshop-measure&colorSelection.png)

**选框工具的多用途**，增（Shift）减（Alt）以及交叉选择（Shift + Alt）。左右（或上下）使用分离选框选择可以得到整两个分离边框的距离总值。

![](../img/T/rect-selection-tool.gif)

所有能接受颜色的属性都需要取色。

- 边框色
- 背景色
- 文字色

NOTE: 使用魔棒工具可以迅速识别背景色是否没*线性*渐变的方法。Mac OS X 推荐使用 **Sip** 可在 Mac App Store 免费下载。

### 切图

修饰性图标和内容性图片需要（在 HTML 的 `<img>` 之中，只需站位不需切图）切出。切出的内容性图片应保存为 `*.jpg` 格式，而修饰性图片因保存为 `png24`（IE6 不支持半透明） 或 `png8` 它们不支持全透明。

**隐藏文字**，方法一，直接在图层中隐藏文字图层。方法二（两种，分别应对于纯色和有背景需要隐藏文本的情况）如下图所示，使用自由变换。

![](../img/B/btn-remove-text.gif)

**PNG24**切图方法
- 移动工具选中所需图层（<kbd>Ctrl</kbd> 多选）
- 右键合并图层（<kbd>Ctrl</kbd> + <kbd>E</kbd>）
- 复制到新图层

**PNG8**带背景切图方法
- 合并可见图层（<kbd>Shift</kbd> + <kbd>Ctrl</kbd> + <kbd>E</kbd>）
- 矩形选框选择内容
- 魔棒工具去除多余部分（<kbd>Alt</kbd> + 选取）

**可平铺**背景的切图方法
- 用矩形选择一个区域
- 复制至新图层

NOTE: X 轴平铺需要占满图片的宽，Y 轴平铺需要占满图片的高。

**切片**工具（大图化小的方法，将一大图分为多小图）
- 拉参考线
- 选择切片工具
- 点击 “基于参考线的切片” 按钮
- 选择切片选择工具
- 保存于新图层

### 保存

将需要的内容保存在独立的文件里便于之后的导出。（存储于 Web 所用格式 <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>Ctrl</kbd> + <kbd>S</kbd>）

如需保存**独立图层**则要把需要的图层拖到新建的透明背景的图层，或在图层上右键复制（Duplicate）图层选择地址为新文件即可。

**图片与背景合并**的切图方法如下

![](../img/S/save-image.gif)

#### 保存格式的选择

保存类型一：色彩丰富切无透明要求时保存为 `JPG` 格式并选用时候的品质（通常使用品质 80 ）。

保存类型二：图片色彩不丰富，不伦透明与否一律保存为 `PNG8` 格式（256颜色，需特殊设置如下图）。

![](../img/P/photoshop-saveFormat.png)

保存类型三：图片有半透明的要求，保存为 `PNG24` 格式（不对图片进行压缩）。

保存类型四：保留 PSD 源文件，以备不时之需。

### 图片修改与维护

维护与修改之一：**更改画布**大小以便增加新素材。

![](../img/R/resize-canvas.gif)

维护与修改之二：移动图标分两种，独立图层（移动工具拖动），于非独立图层（选取工具选中分离后移动工具拖动）。

![](../img/M/move-layer.gif)

维护与修改之三：**裁剪画布**的方法有两种，(1)用选取工具选取后图片裁取，(2)直接用裁剪工具裁剪画布。

![](../img/C/crop-canvas.gif)

**注意事项**：为了可维护性的考虑因适当的留出适当的空白区域以便修改所用和提高容错性。`PNG8`需更改图片颜色模式为 RGB 颜色（默认为索引颜色模式，颜色信息会被丢失）。

![](../img/P/png8-color-mode.gif)

### 图片优化与合并

在 HTML 中使用背景图片的方法如下：

```html
<button type="button" class="btn-default">Click Me</button>

<style type="text/css" media="screen">
  .btn-default {
  background: url(image/btn.png) no-repeat 0 0;
}
.btn-default-alt {
background: url(image/sprite.png) no-repeat 0 -50px;
}
</style>
```

图片的**合并**就如同上面提到的切图后保存的过程。拼好的图称之为 **Sprite** 它能减少网络请求次数提高速度。图片压缩工具分为无损（ImageOptim 等工具，也可结合 Grunt 自动化构建工具一同使用）与有损压缩工具（TinyPng）。

合并的图片可以以横向或纵向的排列，分类可将同属于一个模块（功能模块），大小相近（充分利用画布空间），颜色相近（减少文件大小）。

#### 图片的兼容

IE6 不支持 PNG24 半透明所以需要保存两份（sprite.png - png24 和 sprite-ie.png - 8）。在使用 CSS3 是让高级浏览器使用 CSS3 低级浏览器则使用切图。优雅降级指的是让低级浏览器不显示高级浏览器中的界面细节。

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/80x15.png" /></a><br />This work by <a xmlns:cc="http://creativecommons.org/ns#" href="li-xinyang.com" property="cc:attributionName" rel="cc:attributionURL">Li Xinyang</a> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License</a>.
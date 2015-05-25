# 网页制作

## 概述

**网页发展史**

Web 1.0 -> Web 2.0（基于 Ajax） -> Web 3.0 （基于 HTML5）

**协作流程**

![](img/development-flow.png)

**前端职责**

视觉稿（配色图标距离空间） + 交互稿（用户逻辑） = UI （用户界面）

视觉稿 -> [页面制作]

交互稿 -> [页面逻辑开发]

**所需技能**

- DOM (操作 HTML 及 CSS 的接口)
- JavaScript (定义页面互动)
- CSS (定义页面样式)
- HTML (定义页面结果)
- Photoshop (取图)

## Photoshop

**切图** 从设计稿中切除网页的素材并在代码中引入图片 (复杂的图片或者解决兼容问题)

```
// 设计稿 (*.psd) -> 产出物 (*png, *.jpg)

<img src="img/avatar.jpg" alt="desc">

<style type="text/css" media="screen">
  background-image: url(../img/sprite.png);
  background-position: 0 0;
</style>
```

### 工具, 面板, 视图

在全局设置下将单位修改为像素，因其在 CSS 中运用最广。设置工作区布局为切图及图片编辑做准备。

![](img/Screen%20Shot%202015-05-25%20at%201.15.45%20PM.png)

**切图常用工具**

|工具名|示意图|注释|
|------|:----:|----|
|移动工具| ![](img/hwa_03.png)||
|矩形选框工具| ![](img/hwa_01.png)||
|魔棒工具|![](img/hwa_05.png)|（容差 Tolerance 越小学则的范围就越小）|
|剪裁工具| ![](img/hwa_06.png) ||
|切片工具| ![](img/hwa_07.png)||
|缩放工具| ![](img/hwa_34.png)||
|取色器| ![](img/hwa_31.png)||

图层（单层元素）与组（类似于文件夹）的区别。

**辅助视图**，在视图菜单下启动

- 对齐，会启动靠近吸附功能
- 标尺，<kbd>Command</kbd> + <kbd>R</kbd>
- 参考线，<kbd>Command</kbd> + <kbd>;</kbd>

![](img/Screen%20Shot%202015-05-25%20at%205.25.41%20PM.png)

NOTE: 所有工具及快捷键如下。

![](img/v2_Tools%20panel_PS_update1.png)

#### 测量及取色

所有能接受数字的属性都需要测量并尽可能百分百的还原设计稿。

- 宽度，高度 (width, height)
- 内外边距 (padding, margin)
- 边框 (border)
- 定位 (position)
- 文字大小 (font-size)
- 行高 (line-height)
- 背景位置 (background-position)

NOTE: 测量时尽可能放大画布以减少误差。量取文字是为了减少误差尽量选取尺寸大的文字进行测量。

![](img/Screen%20Shot%202015-05-25%20at%207.16.43%20PM.png)

**选框工具的多用途**，增（Shift）减（Alt）以及交叉选择（Shift + Alt）。左右（或上下）使用分离选框选择可以得到整两个分离边框的距离总值。

![](img/rect-selection-tool.gif)

所有能接受颜色的属性都需要取色。

- 边框色
- 背景色
- 文字色

NOTE: 使用魔棒工具可以迅速识别背景色是否没*线性*渐变的方法。Mac OS X 推荐使用 **Sip** 可在 Mac App Store 免费下载。

## 开发及调试工具

- 文本编辑器 && IDE (集成开发环境)
- Google Chrome, Firefox Firebug, Safari Developer Tool

NOTE: [Google Chrome DevTools Doc](https://developer.chrome.com/devtools)
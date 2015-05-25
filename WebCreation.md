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

- 移动工具
- 矩形选框工具
- 魔棒工具
- 剪裁工具 + 切片工具
- 缩放工具
- 取色器

1505251325 14:14

## 开发及调试工具

- 文本编辑器 && IDE (集成开发环境)
- Google Chrome, Firefox Firebug, Safari Developer Tool

NOTE: [Google Chrome DevTools Doc](https://developer.chrome.com/devtools)
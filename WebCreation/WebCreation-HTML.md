<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [HTML](#html)
  - [HTML 历史](#html-%E5%8E%86%E5%8F%B2)
  - [HTML 简介](#html-%E7%AE%80%E4%BB%8B)
  - [HTML 语法](#html-%E8%AF%AD%E6%B3%95)
    - [全局属性](#%E5%85%A8%E5%B1%80%E5%B1%9E%E6%80%A7)
  - [HTML 标签](#html-%E6%A0%87%E7%AD%BE)
    - [文本标签](#%E6%96%87%E6%9C%AC%E6%A0%87%E7%AD%BE)
    - [组合内容标签](#%E7%BB%84%E5%90%88%E5%86%85%E5%AE%B9%E6%A0%87%E7%AD%BE)
    - [嵌入](#%E5%B5%8C%E5%85%A5)
    - [资源标签](#%E8%B5%84%E6%BA%90%E6%A0%87%E7%AD%BE)
      - [图标签](#%E5%9B%BE%E6%A0%87%E7%AD%BE)
      - [热点区域标签](#%E7%83%AD%E7%82%B9%E5%8C%BA%E5%9F%9F%E6%A0%87%E7%AD%BE)
    - [表格](#%E8%A1%A8%E6%A0%BC)
    - [表单](#%E8%A1%A8%E5%8D%95)
    - [语义化](#%E8%AF%AD%E4%B9%89%E5%8C%96)
  - [实体字符](#%E5%AE%9E%E4%BD%93%E5%AD%97%E7%AC%A6)
  - [浏览器兼容](#%E6%B5%8F%E8%A7%88%E5%99%A8%E5%85%BC%E5%AE%B9)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## HTML

### HTML 历史

HTML (Hyper Text Markup Language)，用于标记页面中的内容。

![](../img/H/html-history.png)

### HTML 简介

![](../img/H/html-overview.png)

注意事项：

- `<!DOCTYPE html>` 必须首行定格
- `<title>` 为文档标题
- `<meta charset="utf-8">` 文档解码格式
- `<meta name="keywords" content="...">` 和 `<meta name="description" content="...">` 提供给搜索引擎使用
- `<meta name="viewport" content="width=device-width, initial-scale=1.0">` 移动端浏览器的宽高与缩放
- `<link>` 标签可以引入 favicon 和样式表 CSS 文件

### HTML 语法

![](../img/H/html-syntax.png)

**书写规范**：

- 小写标签和属性
- 属性值双引号
- 代码因嵌套缩进

#### 全局属性

- id, `<div id='unique-element'></div>`，页面中唯一
- class，`<button class='btn'>Click Me</button>`，页面中可重复出现
- style，尽量避免
- title，对于元素的描述类似于 Tooltip 的效果。

### HTML 标签

**[HTML5 标签集合](http://www.html5star.com/manual/html5label-meaning)**

![](../img/H/html-elements.jpg)

**页面通常结构**

![Web Structure](../img/S/structure.gif)

#### 文本标签

```html
<!-- 默认超链接  -->
<a href="http://sample-link.com" title="Sample Link">Sample</a>
<!-- 当前窗口显示 -->
<a href="http://sample-link.com" title="Sample Link" target="_self">Sample</a>
<!-- 新窗口显示 -->
<a href="http://sample-link.com" title="Sample Link" target="_blacnk">Sample</a>
<!-- iframe 中打开链接 -->
<a href="http://sample-link.com" title="Sample Link" target="iframe-name">Sample</a>
<iframe name="iframe-name" frameborder="0"></iframe>

<!-- 页面中的锚点 -->
<a href="#achor">Achor Point</a>
<section id="achor">Achor Content</section>

<!-- 邮箱及电话需系统支持 -->
<a href="mailto:sample-address@me.com" title="Email">Contact Us</a>
<!-- 多个邮箱地址 -->
<a href="mailto:sample-address@me.com, sample-address0@me.com" title="Email">Contact Us</a>
<!-- 添加抄送，主题和内容 -->
<a href="mailto:sample-address@me.com?cc=admin@me.com&subject=Help&body=sample-body-text" title="Email">Contact Us</a>

<!-- 电话示例 -->
<a href="tel:99999999" title="Phone">Ring Us</a>
```

#### 组合内容标签

- `<div>`
- `<p>`
- `<ol>`
- `<ul>`
- `<dl>`
- `<pre>`
- `<blockquote>`

NOTE: `<dl>` 为自定义列表，其中包含一个或多个 `<dt>` 及 一个或多个 `<dd>`，并且`dt` 与 `dl`列表会有缩进的效果。`<pre>` 会保留换行和空格，通常与 `<code>` 一同使用。

```html
<pre>
  <code>
    int main(void) {
      printf('Hello, world!');
      return 0;
    }
  </code>
</pre>
```

`<blockquote>` 拥有 `cite` 属性，它包含引用文本的出处，示例如下所示：

```html
<blockquote cite="http://example.com/facts">
  <p>Sample Quote...</p>
</blockquote>
```

#### 嵌入

```html
<iframe src=""></iframe> 页面操作可以不影响到iframe的内容

<!--object embed通常用来嵌入外部资源 -->
<object type="application/x-shockwave-player">
  <param name="movie" value="book.pdf">
</object>

<!--视频 track可以引入字幕 autoplay可以使视频加载后自动播放，loop可以使其循环播放 -->
<video autoplay loop controls="controls" poster="poster.jpg">
  <source src="movie.mp4" type="video/mp4">
  <source src="movie.webm" type="video/webm">
  <source src="movie.ogg" type="video/ogg">
  <track kind="subtitles" src="video.vtt" srclang="cn" label="cn">
</video>
```
#### 资源标签

##### 图标签
`canvas` 基于像素，性能要求比较高，可用于实时数据展示。`svg` 为矢量图形图像。

##### 热点区域标签

`img`中套用`map`以及`area`可以实现点击某部分图片触发一个链接，点击另一部分触发另一个链接

```html
<img src="mama.jpg" width=100 height=100 usemap="#map" />
<map name="map">
    <area shap="rect" coords="0,0,50,50" href="" alt="">
    <area shap="circle" coords="75,75,25" href="" alt="">
</map>
```

#### 表格

**表格代码示例**

```html
<table>
  <caption>table title and/or explanatory text</caption>
  <thead>
    <tr>
      <th>header</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>data</td>
    </tr>
  </tbody>
</table>
```

使用 `colspan=val` 进行跨列，使用 `rowspan=val` 进行跨行。

#### 表单

```html
<form action="WebCreation_submit" method="get" accept-charset="utf-8">
  <fieldset>
    <legend>title or explanatory caption</legend>
    <!-- 第一种添加标签的方法 -->
    <label><input type="text/submit/hidden/button/etc" name="" value=""></label>
    <!-- 第二种添加标签的方法 -->
    <label for="input-id">Sample Label</label>
    <input type="text" id="input-id">
  </fieldset>
  <fieldset>
    <legend>title or explanatory caption</legend>
    <!-- 只读文本框 -->
    <input type="text" readonly>
    <!-- 隐藏文本框，可提交影藏数据 -->
    <input type="text" name="hidden-info" value="hiden-info-value" hidden>
  </fieldset>
  <button type="submit">Submit</button>
  <button type="reset">Reset</button>
</form>
```

使用`fieldset`可用于对表单进行分区

表单中的其他控件类型：
- `textarea` （文本框）
- `select` 与 `option` （下拉菜单可多选）

<table>
  <caption>input 类型支持值列表</caption>
  <tbody>
  <tr>
    <th style="width:22%">Value</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>button</td>
    <td>Defines a clickable button (mostly used with a JavaScript to activate a script)</td>
  </tr>
  <tr>
    <td>checkbox</td>
    <td>Defines a checkbox</td>
  </tr>
  <tr>
  <td class="html5badge"><img src="../img/H/html5_badge20.png">color</td>
    <td>Defines a color picker</td>
  </tr>
  <tr>
  <td class="html5badge"><img src="../img/H/html5_badge20.png">date</td>
    <td>Defines a date control (year, month and day (no time))</td>
  </tr>
  <tr>
  <td class="html5badge"><img src="../img/H/html5_badge20.png">datetime</td>
    <td>The input type datetime has been removed from the HTML standard. Use datetime-local instead.</td>
    </tr>
    <tr>
    <td class="html5badge"><img src="../img/H/html5_badge20.png">datetime-local</td>
      <td>Defines a date and time control (year, month, day, hour, minute, second, and fraction of a second (no time zone)</td>
      </tr>
      <tr>
      <td class="html5badge"><img src="../img/H/html5_badge20.png">email</td>
        <td>Defines a field for an e-mail address</td>
      </tr>
      <tr>
        <td>file</td>
        <td>Defines a file-select field and a "Browse..." button (for file uploads)</td>
      </tr>
      <tr>
        <td>hidden</td>
        <td>Defines a hidden input field</td>
      </tr>
      <tr>
        <td>image</td>
        <td>Defines an image as the submit button</td>
      </tr>
      <tr>
      <td class="html5badge"><img src="../img/H/html5_badge20.png">month</td>
        <td>Defines a month and year control (no time zone)</td>
      </tr>
      <tr>
      <td class="html5badge"><img src="../img/H/html5_badge20.png">number</td>
        <td>Defines a field for entering a number</td>
      </tr>
      <tr>
        <td>password</td>
        <td>Defines a password field (characters are masked)</td>
      </tr>
      <tr>
        <td>radio</td>
        <td>Defines a radio button</td>
      </tr>
      <tr>
      <td class="html5badge"><img src="../img/H/html5_badge20.png">range</td>
        <td>Defines a control for entering a number whose exact value is not important (like a slider control)</td>
      </tr>
      <tr>
        <td>reset</td>
        <td>Defines a reset button (resets all form values to default values)</td>
      </tr>
      <tr>
      <td class="html5badge"><img src="../img/H/html5_badge20.png">search</td>
        <td>Defines a text field for entering a search string</td>
      </tr>
      <tr>
        <td>submit</td>
        <td>Defines a submit button</td>
      </tr>
      <tr>
      <td class="html5badge"><img src="../img/H/html5_badge20.png">tel</td>
        <td>Defines a field for entering a telephone number</td>
      </tr>
      <tr>
        <td>text</td>
        <td>Default. Defines a single-line text field (default width is 20 characters)</td>
      </tr>
      <tr>
      <td class="html5badge"><img src="../img/H/html5_badge20.png">time</td>
        <td>Defines a control for entering a time (no time zone)</td>
      </tr>
      <tr>
      <td class="html5badge"><img src="../img/H/html5_badge20.png">url</td>
        <td>Defines a field for entering a URL</td>
      </tr>
      <tr>
      <td class="html5badge"><img src="../img/H/html5_badge20.png">week</td>
        <td>Defines a week and year control (no time zone)</td>
      </tr>
    </tbody>
</table>

#### 语义化

语义化（Semantic Tag）是指用合适的标签标识适当的内容，它可以起到搜索引擎优化（Search Engine Optimization），提高可访问性（例如盲人使用的屏幕阅读器），与此同时还可以提高代码的可读性。

### 实体字符

实体字符（ASCII Encoding Reference）是用来在代码中以实体代替与HTML语法相同的字符，避免浏览解析错误。它的两种表示方式，第一种为 `&` 外加实体字符名称，例如 `&nbsp;`，第二种为 `&` 加实体字符序号，例如 `&#160;`。

<table>
    <caption>常用HTML字符实体（建议使用实体）：</caption>
    <thead>
        <tr>
            <th>字符</th>
            <th>名称</th>
            <th>实体名</th>
            <th>实体数</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>&quot;</td>
            <td>双引号</td>
            <td>&amp;quot;</td>
            <td>&amp;#34;</td>
        </tr>
        <tr>
            <td>&amp;</td>
            <td>&amp;符</td>
            <td>&amp;amp;</td>
            <td>&amp;#38;</td>
        </tr>
        <tr>
            <td>&lt;</td>
            <td>左尖括号（小于号）</td>
            <td>&amp;lt;</td>
            <td>&amp;#60;</td>
        </tr>
        <tr>
            <td>&gt;</td>
            <td>右尖括号（大于号）</td>
            <td>&amp;gt;</td>
            <td>&amp;#62;</td>
        </tr>
        <tr>
            <td>&nbsp;</td>
            <td>空格</td>
            <td>&amp;nbsp;</td>
            <td>&amp;#160;</td>
        </tr>
        <tr>
            <td>&#12288;</td>
            <td>中文全角空格</td>
            <td>&nbsp;</td>
            <td>&amp;#12288;</td>
        </tr>
    </tbody>
</table>

<table>
    <caption>常用特殊字符实体（不建议使用实体）：</caption>
    <thead>
        <tr>
            <th>字符</th>
            <th>名称</th>
            <th>实体名</th>
            <th>实体数</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>&yen;</td>
            <td>元</td>
            <td>&amp;yen;</td>
            <td>&amp;#165;</td>
        </tr>
        <tr>
            <td>&brvbar;</td>
            <td>断竖线</td>
            <td>&amp;brvbar;</td>
            <td>&amp;#166;</td>
        </tr>
        <tr>
            <td>&copy;</td>
            <td>版权</td>
            <td>&amp;copy;</td>
            <td>&amp;#169;</td>
        </tr>
        <tr>
            <td>&reg;</td>
            <td>注册商标R</td>
            <td>&amp;reg;</td>
            <td>&amp;#174;</td>
        </tr>
        <tr>
            <td>&trade;</td>
            <td>商标TM</td>
            <td>&amp;trade;</td>
            <td>&amp;#8482;</td>
        </tr>
        <tr>
            <td>&middot;</td>
            <td>间隔符</td>
            <td>&amp;middot;</td>
            <td>&amp;#183;</td>
        </tr>
        <tr>
            <td>&laquo;</td>
            <td>左双尖括号</td>
            <td>&amp;laquo;</td>
            <td>&amp;#171;</td>
        </tr>
        <tr>
            <td>&raquo;</td>
            <td>右双尖括号</td>
            <td>&amp;raquo;</td>
            <td>&amp;#187;</td>
        </tr>
        <tr>
            <td>&deg;</td>
            <td>度</td>
            <td>&amp;deg;</td>
            <td>&amp;#176;</td>
        </tr>
        <tr>
            <td>&times;</td>
            <td>乘</td>
            <td>&amp;times;</td>
            <td>&amp;#215;</td>
        </tr>
        <tr>
            <td>&divide;</td>
            <td>除</td>
            <td>&amp;divide;</td>
            <td>&amp;#247;</td>
        </tr>
        <tr>
            <td>&permil;</td>
            <td>千分比</td>
            <td>&amp;permil;</td>
            <td>&amp;#8240;</td>
        </tr>
    </tbody>
</table>

NOTE：具体所需可在使用时查询，无需记忆。

### 浏览器兼容

主流浏览器都兼容 HTML5 的新标签，对于 IE8 及以下版本不认识 HTML5的新元素，可以使用 JavaScript 创建一个没用的元素来解决，例如：

```javascript
<script>
    document.createElement("header");
</script>
```
也可以使用 shiv 来解决兼容性问题，详情可参考 [HTML5 Shiv](https://github.com/afarkas/html5shiv)

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/80x15.png" /></a><br />This work by <a xmlns:cc="http://creativecommons.org/ns#" href="li-xinyang.com" property="cc:attributionName" rel="cc:attributionURL">Li Xinyang</a> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License</a>.
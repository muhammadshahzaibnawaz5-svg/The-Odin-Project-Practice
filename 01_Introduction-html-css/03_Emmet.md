### Syntax

#### Child: `>`
```emmet
nav>ul>li
```
```html
<nav>
    <ul>
        <li></li>
    </ul>
</nav>
```

#### Sibling: `+`
```emmet
div+p+bq
```
```html
<div></div>
<p></p>
<blockquote></blockquote>
```

#### Climb-up: `^`
```emmet
div+div>p>span+em^bq
```
```html
<div></div>
<div>
    <p><span></span><em></em></p>
    <blockquote></blockquote>
</div>
```

```emmet
div+div>p>span+em^^bq
```
```html
<div></div>
<div>
    <p><span></span><em></em></p>
</div>
<blockquote></blockquote>
```

#### Grouping: `()`
```emmet
div>(header>ul>li*2>a)+footer>p
```
```html
<div>
    <header>
        <ul>
            <li><a href=""></a></li>
            <li><a href=""></a></li>
        </ul>
    </header>
    <footer>
        <p></p>
    </footer>
</div>
```

```emmet
(div>dl>(dt+dd)*3)+footer>p
```
```html
<div>
    <dl>
        <dt></dt><dd></dd>
        <dt></dt><dd></dd>
        <dt></dt><dd></dd>
    </dl>
</div>
<footer>
    <p></p>
</footer>
```

#### Multiplication: `*`
```emmet
ul>li*5
```
```html
<ul>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
</ul>
```

#### Item numbering: `$`
```emmet
ul>li.item$*5
```
```html
<ul>
    <li class="item1"></li>
    <li class="item2"></li>
    <li class="item3"></li>
    <li class="item4"></li>
    <li class="item5"></li>
</ul>
```

```emmet
h$[title=item$]{Header $}*3
```
```html
<h1 title="item1">Header 1</h1>
<h2 title="item2">Header 2</h2>
<h3 title="item3">Header 3</h3>
```

```emmet
ul>li.item$$$*5
```
```html
<ul>
    <li class="item001"></li>
    <li class="item002"></li>
    <li class="item003"></li>
    <li class="item004"></li>
    <li class="item005"></li>
</ul>
```

```emmet
ul>li.item$@-*5
```
```html
<ul>
    <li class="item5"></li>
    <li class="item4"></li>
    <li class="item3"></li>
    <li class="item2"></li>
    <li class="item1"></li>
</ul>
```

```emmet
ul>li.item$@3*5
```
```html
<ul>
    <li class="item3"></li>
    <li class="item4"></li>
    <li class="item5"></li>
    <li class="item6"></li>
    <li class="item7"></li>
</ul>
```

#### ID & Class attributes
```emmet
#header
```
```html
<div id="header"></div>
```

```emmet
.title
```
```html
<div class="title"></div>
```

```emmet
form#search.wide
```
```html
<form id="search" class="wide"></form>
```

```emmet
p.class1.class2.class3
```
```html
<p class="class1 class2 class3"></p>
```

#### Custom attributes
```emmet
p[title="Hello world"]
```
```html
<p title="Hello world"></p>
```

```emmet
td[rowspan=2 colspan=3 title]
```
```html
<td rowspan="2" colspan="3" title=""></td>
```

```emmet
div[a='value1' b="value2"]
```
```html
<div a="value1" b="value2"></div>
```

#### Text: `{}`
```emmet
a{Click me}
```
```html
<a href="">Click me</a>
```

```emmet
p>{Click }+a{here}+{ to continue}
```
```html
<p>Click <a href="">here</a> to continue</p>
```

#### Implicit tag names
```emmet
.class
```
```html
<div class="class"></div>
```

```emmet
em>.class
```
```html
<em><span class="class"></span></em>
```

```emmet
ul>.class
```
```html
<ul>
    <li class="class"></li>
</ul>
```

```emmet
table>.row>.col
```
```html
<table>
    <tr class="row">
        <td class="col"></td>
    </tr>
</table>
```

### HTML Abbreviations

```emmet
!
```
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
</body>
</html>
```

```emmet
a
```
```html
<a href=""></a>
```

```emmet
a:link
```
```html
<a href="http://"></a>
```

```emmet
a:mail
```
```html
<a href="mailto:"></a>
```

```emmet
abbr
```
```html
<abbr title=""></abbr>
```

```emmet
base
```
```html
<base href="">
```

```emmet
br
```
```html
<br>
```

```emmet
hr
```
```html
<hr>
```

```emmet
link
```
```html
<link rel="stylesheet" href="">
```

```emmet
link:css
```
```html
<link rel="stylesheet" href="style.css">
```

```emmet
link:favicon
```
```html
<link rel="shortcut icon" type="image/x-icon" href="favicon.ico">
```

```emmet
meta:vp
```
```html
<meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
```

```emmet
style
```
```html
<style></style>
```

```emmet
script
```
```html
<script></script>
```

```emmet
script:src
```
```html
<script src=""></script>
```

```emmet
img
```
```html
<img src="" alt="">
```

```emmet
picture
```
```html
<picture></picture>
```

```emmet
form
```
```html
<form action=""></form>
```

```emmet
form:get
```
```html
<form action="" method="get"></form>
```

```emmet
form:post
```
```html
<form action="" method="post"></form>
```

```emmet
label
```
```html
<label for=""></label>
```

*(Many more input variants exist — e.g. `input:text`, `input:email`, `input:password`, `input:checkbox`, `textarea`, `select`, `option`, `button`, etc. Just type `input:` + type for quick forms.)*

### CSS Abbreviations (most common)

#### Visual Formatting
```emmet
pos
```
```css
position: relative;
```

```emmet
pos:a
```
```css
position: absolute;
```

```emmet
d
```
```css
display: block;
```

```emmet
d:f
```
```css
display: flex;
```

```emmet
fl
```
```css
float: left;
```

```emmet
ov
```
```css
overflow: hidden;
```

#### Margin & Padding
```emmet
m
```
```css
margin: ;
```

```emmet
mt
```
```css
margin-top: ;
```

```emmet
p
```
```css
padding: ;
```

#### Box Sizing
```emmet
bxz
```
```css
box-sizing: border-box;
```

#### Font
```emmet
f
```
```css
font: ;
```

```emmet
fw
```
```css
font-weight: ;
```

```emmet
fs
```
```css
font-style: italic;
```

```emmet
fz
```
```css
font-size: ;
```

```emmet
ff
```
```css
font-family: ;
```

#### Text
```emmet
ta
```
```css
text-align: left;
```

```emmet
td
```
```css
text-decoration: none;
```

```emmet
va
```
```css
vertical-align: top;
```


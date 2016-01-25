# jquery.stickymenu.js
基于jquery的粘性菜单插件

1、轻量级的粘性菜单插件，基于jquery，源码不超过7kb


### 基本使用
#### html
```
<ul class="nav">
    <li class="active"><a href="#section1">Section1</a></li>
    <li><a href="#section2">Section2</a></li>
    <li><a href="#section3">Section3</a></li>
    <li><a href="#section4">Section4</a></li>
    <li><a href="#section5">Section5</a></li>
    <li class="exceptLink"><a href="javascript:;">ExceptLink</a></li>
</ul>
<div class="section section1" style="background:#00ff90">
    <p class="title">Section1</p>
</div>
<div class="section section2" style="background:#00ff21">
    <p class="title">Section2</p>
</div>
<div class="section section3" style="background:#0094ff">
    <p class="title">Section3</p>
</div>
<div class="section section4" style="background:#ff6a00">
    <p class="title">Section4</p>
</div>
<div class="section section5" style="background:#6c45b6">
    <p class="title">Section5</p>
</div>
```

#### css
```
html, body, a { font-family: 'Microsoft YaHei'; color: #000; }
html, body, div, p, ul, li { margin: 0; padding: 0; }
ul, li { list-style-type: none; }
a { text-decoration: none; }
.nav { margin: 0 auto; padding-left: 10%; height: 60px; background: #00ff21; }
    .nav li { float: left; text-align: center; line-height: 60px; }
    .nav a { display: block; width: 180px; height: 60px; }
    .nav .active, .nav li:hover { background: #226d13; }
.section { height: 600px; overflow: hidden; }
.title { margin: 250px; font-size: 50px; text-align: center; }
```

#### script
```
<script src="http://luopq.com/demo/lib/jquery-1.10.2.min.js"></script>
<script src="../src/jquery.stickymenu.js"></script>
<script>
    $(".nav").stickymenu({
        "stickyBarSelector": ".nav",
        "menuItemSelector": "li",
    });
</script>
</script>
```
#### Demo

1.<a href="http://luopq.com/demo/stickymenu/examples/index.html" target="_blank">Demo1</a>

2.<a href="http://luopq.com/demo/osum/index.html" target="_blank">Demo2</a>


#### options
| 参数名 | 类型 |默认值|描述|
| ----  | ---- |-----|---|
|speed|number|500|跳到指定区域的滚动时间，单位毫秒|
|activeClass|string|"active"|菜单选中样式类名|
|menuTop|number|0|菜单顶部距离浏览器视口距离，单位px|
|onItemSelected|function|null|选择菜单项后回调函数|
|stickyClass|string|"sticky"|菜单固定后的样式类名|
|stickyBarSelector|string|undefined|菜单选择器，不传则为调用元素本身|
|stickyBarHeight|number|undefined|菜单的高度，不传则自动获取|

如果某个连接没有对应区域，则添加class="exceptLink"即可
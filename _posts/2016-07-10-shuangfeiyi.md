---
layout: post
title: "CSS 双飞翼布局"
date: 2016-07-11 03:08:45 +0700
categories: [CSS]
---




双飞翼布局：总共分三栏，左侧栏Left，中间主栏Main，右侧栏Right

第一步，建立三个div，不过注意，中间Main需要加一个wrap div. 整个结构看起来是这样的：


```html

<style type="text/css">
	.mainWrap-1
	{
		width: 100%;
		background: #ccc;
	}
	.main-1
	{
		margin-left: 210px; /*左侧栏的宽度为200px，此处设置为210px，是为了留出10px的间隔*/
		margin-right: 310px;/*左侧栏的宽度为300px，此处设置为310px，是为了留出10px的间隔*/
		background: #c33;
	}
	.left-1
	{
		width: 200px;
		height: 300px;
		background: skyblue;
	}
	.right-1
	{
		width: 300px;
		height: 300px;
		background: green;
	}
</style>

<div class="mainWrap-1">	<div class="main-1"></div></div>   
<div class="left-1"></div>
<div class="right-1"></div>

```


<br>
<style type="text/css">
	.mainWrap-1
	{
		width: 100%;
		background: #ccc;
	}
	.main-1
	{
		margin-left: 210px; /*左侧栏的宽度为200px，此处设置为210px，是为了留出10px的间隔*/
		margin-right: 310px;/*左侧栏的宽度为300px，此处设置为310px，是为了留出10px的间隔*/
		background: #c33;
		height: 100px;
		color: #fff;
	}
	.left-1
	{
		width: 200px;
		height: 100px;
		background: skyblue;
		color: #fff;
	}
	.right-1
	{
		width: 300px;
		height: 100px;
		background: green;
		color: #fff;
	}

	.clearFloat
	{
		clear: both;
	}
</style>

<div class="mainWrap-1">	<div class="main-1">Main,<br>margin-left:210px; <br>margin-right:310px;</div></div>   
<div class="left-1">Left <br>width:200px;</div>
<div class="right-1">Right <br> width:300px;</div>

<div class="clearFloat"></div>

<br>

看起来很混乱，对不对？
<br>

第二步：动起来！

A, mainWrap,left和right添加float：left；注意，main不添加！！<br>
B, left 左移动100%的宽度：margin-left:-100%;<br>
C, right左移动自身的宽度：margin-left:-300px;

<br>

<style type="text/css">
	.mainWrap-2
	{
		width: 100%;
		background: #ccc;
		float: left;
		margin-bottom: 50px;
	}
	.main-2
	{
		margin-left: 210px; /*左侧栏的宽度为200px，此处设置为210px，是为了留出10px的间隔*/
		margin-right: 310px;/*左侧栏的宽度为300px，此处设置为310px，是为了留出10px的间隔*/
		background: #c33;
		height: 100px;
		color: #fff;
	}
	.left-2
	{
		width: 200px;
		height: 100px;
		background: skyblue;
		color: #fff;float: left;
		margin-left: -100%;
		
	}
	.right-2
	{
		width: 300px;
		height: 100px;
		background: green;
		color: #fff;
		float: left;
		margin-left: -300px;
	}

</style>

<div class="mainWrap-2"><div class="main-2">Main</div></div>   
<div class="left-2">Left  <br>float:left; <br> margin-left:-100%;</div>
<div class="right-2">Right <br> float:left; <br>margin-left:-300px;</div>

<br>

这就是双飞翼布局了！左右两侧宽度固定，中间主栏宽度自适应，而且，优先加载中间主栏内容，用户体验更好！
<br><br>双飞翼布局，你值得拥有！

























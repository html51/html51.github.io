title: HTML5/CSS3弹出层，适合移动PC
date: 2015-12-09 23:12:45
categories:
- HTML5
tags: [HTML5,css3,移动,弹出层]

-------
随着CSS3的特性越来越完善和标准化，给开发人员在日常的开发过程中带来了非常方便。而且和javascript相比，达到了相同的效果。这次通过CSS3来实现一个弹窗层效果，方便日后再项目的开发中，提高效率。

> * 项目当中经常会有弹出层的需求
> * 在开发中节约时间
> * 适合PC移动端，实用性比较强

#### **html**
``` javascript
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8">
	<title>HTML5/CSS3弹出层，适合移动PC</title>
	<!-- Demo Styles -->
	<link href="css/demo.css" rel="stylesheet">

	<!-- Modal Styles -->
	<link href="css/modal.css" rel="stylesheet">
</head>

<body>
	<div class="container">
		<h2>HTML5/CSS3弹出层，适合移动PC</h2>
		<p>随着CSS3的特性越来越完善和标准化，给开发人员在日常的开发过程中带来了非常方便。而且和javascript相比，达到了相同的效果。这次通过CSS3来实现一个弹窗层效果，方便日后再项目的开发中，提高效率。</p>
		<p><a href="#modal" class="btn go">快来点我</a></p>
	</div>

	<div id="modal">
		<div class="modal-content">
			<div class="header">
				<h2>HTML5/CSS3弹出层，适合移动PC</h2>
			</div>
			<div class="copy">
				<p>随着CSS3的特性越来越完善和标准化，给开发人员在日常的开发过程中带来了非常方便。而且和javascript相比，达到了相同的效果。这次通过CSS3来实现一个弹窗层效果，方便日后再项目的开发中，提高效率。</p>
			</div>
			<div class="cf footer">
				<a href="#" class="btn">关闭</a>
			</div>
		</div>
		<div class="overlay"></div>
	</div>
</body>
</html>
```
<!-- more -->

#### **demo.css**
``` javascript
html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, embed, 
figure, figcaption, footer, header, hgroup, 
menu, nav, output, ruby, section, summary,
time, mark, audio, video {
	margin: 0;
	padding: 0;
	border: 0;
	font-size: 100%;
	font: inherit;
	vertical-align: baseline;
}
body {
	line-height: 1;
}
ol, ul {
	list-style: none;
}
blockquote, q {
	quotes: none;
}
blockquote:before, blockquote:after,
q:before, q:after {
	content: '';
	content: none;
}
table {
	border-collapse: collapse;
	border-spacing: 0;
}

/********* CLEARFIX *********/
.cf:before,
.cf:after {
    content:"";
    display:table;
}
.cf:after {
    clear:both;
}

/******** DEMO STYLES ********/
.container {
	margin:0 auto;
	width:960px;
}

.btn {
	background-color: #f6f6f6;
	background-image: -webkit-gradient(linear, left top, left bottom, from(rgb(246, 246, 246)), to(rgb(225, 225, 225)));
	background-image: -webkit-linear-gradient(top, rgb(246, 246, 246), rgb(225, 225, 225));
	background-image: -moz-linear-gradient(top, rgb(246, 246, 246), rgb(225, 225, 225));
	background-image: -o-linear-gradient(top, rgb(246, 246, 246), rgb(225, 225, 225));
	background-image: -ms-linear-gradient(top, rgb(246, 246, 246), rgb(225, 225, 225));
	background-image: linear-gradient(top, rgb(246, 246, 246), rgb(225, 225, 225));
	filter: progid:DXImageTransform.Microsoft.gradient(GradientType=0,StartColorStr='#f6f6f6', EndColorStr='#e1e1e1');
	border: 1px solid #ccc;
	color:#555;
	display:inline-block;
	padding:5px 15px;
	text-decoration:none;
	text-shadow:0 2px rgba(255,255,255,.9);
	border-radius:20px;
	-moz-border-radius:20px;
	-webkit-border-radius:20px;
	box-shadow:0 1px rgba(0,0,0,.35);
	-moz-box-shadow:0 1px rgba(0,0,0,.35);
	-webkit-box-shadow:0 1px rgba(0,0,0,.35);
}
	.btn:active {
		background-color: #f6f6f6;
		background-image: -webkit-gradient(linear, left bottom, left top, from(rgb(246, 246, 246)), to(rgb(225, 225, 225)));
		background-image: -webkit-linear-gradient(bottom, rgb(246, 246, 246), rgb(225, 225, 225));
		background-image: -moz-linear-gradient(bottom, rgb(246, 246, 246), rgb(225, 225, 225));
		background-image: -o-linear-gradient(bottom, rgb(246, 246, 246), rgb(225, 225, 225));
		background-image: -ms-linear-gradient(bottom, rgb(246, 246, 246), rgb(225, 225, 225));
		background-image: linear-gradient(bottom, rgb(246, 246, 246), rgb(225, 225, 225));
		filter: progid:DXImageTransform.Microsoft.gradient(GradientType=0,StartColorStr='#f6f6f6', EndColorStr='#e1e1e1');
	}
	.btn.go {
		background-color: #3dda38;
		background-image: -webkit-gradient(linear, left top, left bottom, from(rgb(61, 218, 56)), to(rgb(39, 187, 63)));
		background-image: -webkit-linear-gradient(top, rgb(61, 218, 56), rgb(39, 187, 63));
		background-image: -moz-linear-gradient(top, rgb(61, 218, 56), rgb(39, 187, 63));
		background-image: -o-linear-gradient(top, rgb(61, 218, 56), rgb(39, 187, 63));
		background-image: -ms-linear-gradient(top, rgb(61, 218, 56), rgb(39, 187, 63));
		background-image: linear-gradient(top, rgb(61, 218, 56), rgb(39, 187, 63));
		filter: progid:DXImageTransform.Microsoft.gradient(GradientType=0,EndColorStr='#3dda38', StartColorStr='#27bb3f');
		border: 1px solid #21ac1c;
		color:#fff;
		text-shadow:0 -1px rgba(0,0,0,.4);
	}
		.btn.go:active {
			background-color: #3dda38;
			background-image: -webkit-gradient(linear, left bottom, left top, from(rgb(61, 218, 56)), to(rgb(39, 187, 63)));
			background-image: -webkit-linear-gradient(bottom, rgb(61, 218, 56), rgb(39, 187, 63));
			background-image: -moz-linear-gradient(bottom, rgb(61, 218, 56), rgb(39, 187, 63));
			background-image: -o-linear-gradient(bottom, rgb(61, 218, 56), rgb(39, 187, 63));
			background-image: -ms-linear-gradient(bottom, rgb(61, 218, 56), rgb(39, 187, 63));
			background-image: linear-gradient(bottom, rgb(61, 218, 56), rgb(39, 187, 63));
			filter: progid:DXImageTransform.Microsoft.gradient(GradientType=0,EndColorStr='#3dda38', StartColorStr='#27bb3f');
		}

body {
	background:#eee;
	font: 16px/24px Helvetica, sans-serif;
	padding: 30px 0;
}
p {
	margin-bottom:20px;
}

h2 {
	font:600 27px/33px Helvetica, sans-serif;
	margin-bottom:20px;
}
```
#### **modal.css**
``` javascript
/* Normal styles for the modal */
#modal {
	left:50%;
	margin:-250px 0 0 -40%;
	opacity: 0;
	position:absolute;
	top:-50%;
	visibility: hidden;
	width:80%;
	box-shadow:0 3px 7px rgba(0,0,0,.25);
	box-sizing:border-box;
	transition: all 0.4s ease-in-out;
	-moz-transition: all 0.4s ease-in-out;
	-webkit-transition: all 0.4s ease-in-out;
}
	/* Make the modal appear when targeted */
	#modal:target {
		opacity: 1;
		top:50%;
		visibility: visible;
	}
#modal .header,#modal .footer {
	border-bottom: 1px solid #e7e7e7;
	border-radius: 5px 5px 0 0;
}
	#modal .footer {
		border:none;
		border-top: 1px solid #e7e7e7;
		border-radius: 0 0 5px 5px;
	}
#modal h2 {
	margin:0;
}
#modal .btn {
	float:right;
}
#modal .copy,#modal .header, #modal .footer {
	padding:15px;
}
.modal-content {
	background: #f7f7f7;
	position: relative;
	z-index: 20;
	border-radius:5px;
}
#modal .copy {
	background: #fff;
}

#modal .overlay {
	background-color: #000;
	background: rgba(0,0,0,.5);
	height: 100%;
	left: 0;
	position: fixed;
	top: 0;
	width: 100%;
	z-index: 10;
}
```

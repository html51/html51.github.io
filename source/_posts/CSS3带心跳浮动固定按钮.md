title: CSS3带心跳浮动固定按钮
date: 2015-12-10 23:12:45
categories:
- CSS3
tags: [HTML5,css3,移动,固定按钮,浮动]


-------

> 工作之余，学习了一下CSS3属性，希望日后也能用的到。这个按钮的实现效果，主要是结合transform属性和animation属性来实现。

#### **html**
``` javascript
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>CSS3带心跳浮动固定按钮</title>
</head>
<body>
	<div class="post_btn" style="display: block;">
    	<a class="f_post" path="#" data-click-from="post" rel="nofollow">按钮</a>
	</div>

</body>
</html>
```
<!-- more -->

#### **css**
``` javascript
	.post_btn {
	    width: 53px;
	    height: 53px;
	    border-radius: 53px;
	    -webkit-border-radius: 53px;
	    -moz-border-radius: 53px;
	    position: fixed;
	    right: 13px;
	    bottom: 65px;
	    background-color: #f36c2e;
	    display: none;
	    -ms-animation: heart_beat .4s linear;
	    animation: heart_beat .4s linear;
	    -moz-animation: heart_beat .4s linear;
	    -webkit-animation: heart_beat .4s linear;
	    z-index: 999;
	}
	.f_post {
	    color: #FFF;
	    font-size: 10px;
	    margin: 0 auto;
	    padding: 8px 0;
	    overflow: hidden;
	    display: block;
	    text-align: center;
	}
	.f_post::before {
	    background-color: #ffcc00;
	    content: '';
	    display: block;
	    height: 19px;
	    margin: 0 auto 4px;
	    width: 19px;
	}
	@-moz-keyframes heart_beat{
		0%{
			-moz-transform:scale(0);
			opacity:0;
		}
		50%{
			-moz-transform:scale(1.5);
			opacity:1;
		}
		100%{
			-moz-transform:scale(1);
		}
	}
	@-webkit-keyframes heart_beat{
		0%{
			-webkit-transform:scale(0);
			opacity:0;
		}
		50%{
			-webkit-transform:scale(1.5);
			opacity:1;
		}
		100%{
			-webkit-transform:scale(1);
		}
	}
```

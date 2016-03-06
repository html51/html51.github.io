title: jquery锚点带动画跳转，右侧导航点击对应主内容楼层实践
date: 2015-12-14 20:20:45
categories:
- JavaScript
tags: [JavaScript,css,jquery,右侧导航]

-------
> 圣诞节活动，做了一个右侧导航点击和主内容的楼层进行对应。实现过程中遇到了一点小问题，每次点击，都会触发滚动，所以总结一下，希望以后的项目也有所帮助

> * 锚点链接实现
> * 滚动效果的实现

#### **html**
``` javascript
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8">
	<title>项目当中右侧导航与主内容楼层实践</title>
	<!-- Demo Styles -->
	<link href="css/demo.css" rel="stylesheet">

</head>

<body>
	<!--S main-->
    <div class="main">
    	<div class="container">
    		<!--S layer1-->	
    		<div class="layer1"></div>
    		<!--S layer2-->	
    		<div class="layer2" id="002"></div>
    		<!--S layer1-->	
    		<div class="layer3" id="003"></div>
    		<!--S layer1-->	
    		<div class="layer4" id="004"></div>
    		<!--S layer1-->	
    		<div class="layer5"></div>
    	</div>
    	<div class="float">
        	<ul>
        		<li><a href="#002" class="md2" title="Lucky Draw">Lucky Draw</a></li>
        		<li><a href="#003" class="md3" title="Free Shipping">Free Shipping</a></li>
        		<li><a href="#004" class="md4" title="Discount Off">Discount Off</a></li>
        		<li><a href="javascript:void(0);" class="md_backtop" title="返回顶部">返回顶部</a></li>
        	</ul>
        </div>
    </div>
</body>
</html>
```
<!-- more -->

#### **demo.css**
``` javascript
*{
	margin: 0;
	padding: 0;
}
ul,li{
	list-style: none;
}
.main{
	height:2000px;
}
.container{
	width: 980px;
	margin: 0 auto;

}
/*S topbanner*/
.layer1{
	height: 625px;
	background-color:#5d9281; 
}
.layer2{
	height: 666px;
	background-color:#2e574a;
}
.layer3{
	height: 672px;
	background-color:#ffedce;
}
.layer4{
	height: 742px;
	background-color:#84c1a3;
}
.layer5{
	height: 295px;
	background-color:#ffedce;
}
/* S float */
.float,.float a:hover,.float .on a{
    background-image:url(http://www.etradesupply.com/skin/frontend/default/ets2015/images/christmas2015/christmas_float.png);
}
.float{
    width:170px;
    height:250px;
    position: fixed;
    top:40px;
    left: 50%;
    display: none;
    overflow: hidden; 
    background-repeat:no-repeat;
    margin-left:450px; 
    padding-top:70px; 
    z-index:50;
}
.float a{
    width:170px;
    height:40px;
    display: block;
    text-indent: -9999px;
    overflow: hidden;
}
.float .md2:hover,.float .on .md2{
    background-position:-189px -70px;
}
.float .md3:hover,.float .on .md3{
    background-position:-189px -110px;
}
.float .md4:hover,.float .on .md4{
    background-position:-189px -150px;
}
.float .md_backtop:hover{
    background-position:-189px -190px;
}
.float .md_backtop{ 
    height:60px;
}
```
#### **demo.js**
``` javascript
(function($){

    $(function(){
        var inClickState = false;
        $('a[href*=#],area[href*=#]').click(function() {
            //$(this).parent().find("li").removeClass("on");
            //$(this).addClass('on').siblings().removeClass('on');
            inClickState = true;
            var _this = $(this);
            if (location.pathname.replace(/^\//, '') == this.pathname.replace(/^\//, '') && location.hostname == this.hostname) {
                var $target = $(this.hash);
                $target = $target.length && $target || $('[name=' + this.hash.slice(1) + ']');
                if ($target.length) {
                    var targetOffset = $target.offset().top;
                    $('html,body').animate({
                        scrollTop: targetOffset
                    }, 300, function(){
                        $(".float li").removeClass("on");
                         _this.parent('li').addClass("on").siblings().removeClass("on");
                         inClickState = false;
                    });
                    return false;
                };
            };

        });

        $(window).scroll(function(){
            var subNav_on = $(".on");
            var subNav_scroll = function(target){
                subNav_on.removeClass("on");
                console.log(inClickState)
                if(!inClickState){
                    target.parent().addClass("on").siblings().removeClass("on");                    
                }
                subNav_on = target.parent();
            }
            var $this = $(this);
            var targetTop = $(this).scrollTop();
            //console.log(targetTop);
            
            if(targetTop<625){
                subNav_scroll($(".md2"))
            }else if(targetTop>1291 && targetTop<1963){
                subNav_scroll($(".md3"))
            }else if(targetTop>1963){
                subNav_scroll($(".md4"))
            }

            if($(window).scrollTop()>300){
                $(".float").fadeIn("slow");
            }else{
                $(".float li").removeClass("on");
                $(".float").fadeOut("slow").find("a").removeClass('on');
            };
        });

        $(".md_backtop").click(function(){
            inClickState = true;
            $('html, body').animate({scrollTop: 0}, 200, function(){
                inClickState = false;
            });
        })

    })
   
})(jQuery);
```

title: 手机端访问PC端页面检测弹窗，并记录cookie
date: 2015-12-15 20:10:45
categories:
- JavaScript
tags: [JavaScript,cookie,弹窗]

-------

> 主要的需求是用户使用手机访问PC端页面，这个时候告诉用户是否继续留在PC端页面，还是直接跳转到手机端页面进行访问。点击按钮的过程中，并记录cookie，有效时间一天。

#### **html**
``` javascript
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	<!--S popupbox-->
<div class="popup-bg">
    <div class="popup-box">
        <div class="popup-inner">
            <div class="epopup-main">
                <div class="epopup-bd">
                    <p>Enter into Mobile Version?<p>
                </div>
                <div class="epopup-btn-group">
                    <button type="button" data-role="button" class="epopup-btn epopup-btn-ok">Yes</button>
                    <button type="button" data-role="button" class="epopup-btn epopup-btn-cancel">No</button>
                </div>
            </div><!--E epopup-main-->
        
        </div>
    </div>
</div>
<!--E popupbox-->
</body>
</html>
```
<!-- more -->

#### **css**
``` javascript
/* S add popup for mobile */
html.touch,
html.touch body{
	width: 100%;
    height: 100%;
    overflow: hidden;
}
.popup-bg {
    position: fixed;
    top:0;
    left:0;
    height:100%;
    width:100%;
    background-color: rgba(0,0,0,.6);
    z-index: 99999;
    overflow: hidden;
    
    -webkit-box-orient: horizontal;
    -moz-box-orient: horizontal;
    -ms-box-orient: horizontal;
    box-orient: horizontal;
    -webkit-box-pack: center;
    -moz-box-pack: center;
    -ms-box-pack: center;
    box-pack: center;
    -webkit-box-align: center;
    -moz-box-align: center;
    -ms-box-align: center;
    box-align: center;
    display: none;
}
.popup-box {
    position: relative;
    top:50%;
    left:0;
    margin:auto;
    -webkit-transform: translateY(-50%);
    -ms-transform: translateY(-50%);
    -o-transform: translateY(-50%);
    transform: translateY(-50%);
    background-color: #ffffff;
    width:85%;

    border: 1px solid #c5c5c5;
    box-shadow: 1px 1px 1px #e2e1e1;
}
.popup-inner{
    padding: 2rem 1rem;
}
.popup-box .epopup-main {
    display: block;
    background-color: transparent;
}
.epopup-bd{
    display: -webkit-box; 
    display: -moz-box;    
    display: box; 
    -webkit-box-pack: center;
    -moz-box-pack: center;
    -ms-box-pack: center;
    box-pack: center;
    -webkit-box-align: center;
    -moz-box-align: center;
    -ms-box-align: center;
    box-align: center;
    -webkit-box-orient: vertical;
    -moz-box-orient: vertical;
    -ms-box-orient: vertical;
    box-orient: vertical;
}
.epopup-bd p{
    font-size: 1rem;
}
.epopup-btn-group{
    width:80%;
    overflow:hidden;
    margin: 1.5rem auto 0;
}
.epopup-btn{
    border-radius: 2px;
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    border:0;
    font-size: 1rem;
}
.epopup-btn-group .epopup-btn{
    display: block;
    text-align: center;
    padding: 1rem 0;
    line-height:.3rem;
    width:45%;
    
}
.epopup-btn-group button.epopup-btn-ok{
    border:1px solid #6699cc;
    background-color:#6699cc;
    color:#ffffff;
    float: left;   
}
.epopup-btn-group button.epopup-btn-cancel{
    border:1px solid #cccccc;
    background-color:#fcfcfc;
    color:#333333;
    float:right;
}

@media only screen and (min-device-width : 768px) and (max-device-width : 1024px){
    .popup-box{
        width:85%;       
    }
}

@media only screen and (-webkit-device-pixel-ratio: 2) and (device-aspect-ratio: 2/3) {
    .epopup-bd p{
        font-size: 1rem;
    }
    .epopup-btn-group .epopup-btn{
        padding: 1rem 0;
    }
    .epopup-btn{
        font-size: 1rem;
    }

}
```
#### **javascript**
``` javascript
jQuery(function($){

    //alert(1);

    var browser={    
            versions:function(){     
               var u = navigator.userAgent, app = navigator.appVersion;     
               return {//移动终端浏览器版本信息     
                    trident: u.indexOf('Trident') > -1, //IE内核    
                    presto: u.indexOf('Presto') > -1, //opera内核    
                    webKit: u.indexOf('AppleWebKit') > -1, //苹果、谷歌内核    
                    gecko: u.indexOf('Gecko') > -1 && u.indexOf('KHTML') == -1, //火狐内核    
                    mobile: !!u.match(/AppleWebKit.*Mobile.*/), //是否为移动终端    
                    ios: !!u.match(/\(i[^;]+;( U;)? CPU.+Mac OS X/), //ios终端    
                    android: u.indexOf('Android') > -1 || u.indexOf('Linux') > -1, //android终端或者uc浏览器    
                    iPhone: u.indexOf('iPhone') > -1 , //是否为iPhone或者QQHD浏览器    
                    iPad: u.indexOf('iPad') > -1, //是否iPad      
                    webApp: u.indexOf('Safari') == -1 //是否web应该程序，没有头部与底部    
                };    
             }(),    
            language:(navigator.browserLanguage || navigator.language).toLowerCase()
        }

    //判断网站访问模式 
        if(browser.versions.mobile || browser.versions.ios || browser.versions.android || browser.versions.iPhone || browser.versions.iPad){   

            $("html").addClass("touch");      

            // cookie没过期,1天内跳mobile端
            if ($.cookie("mobileCookie")) {
                window.location = "http://m.etradesupply.com";
            }

            // cookie没过期,1天内直接跳PC端
            if ($.cookie("pcCookie")) {
                //window.location = "http://www.etradesupply.com";
            }

            // cookie没过期
            if ($.cookie("mobileCookie") || $.cookie("pcCookie")) {
                $(".popup-bg").hide();
            } else {
                // 过期后显示 or 第一次
                $(".popup-bg").show();
            }
        }else{
            // PC端隐藏
            $(".popup-bg").hide();
            //$("html").removeClass("touch");        
        }     
     
    // pc
    $(".epopup-btn-cancel").on("click", function(){
        $("html").removeClass("touch");

        $('.popup-bg').hide();
        // set pc cooki
        $.cookie("pcCookie","true",{expires:1})
    })

    // mobile
    $(".epopup-btn-ok").on("click", function(){
        $('.popup-bg').hide().fadeOut(500);
        // set mobile cookie
        $.cookie("mobileCookie","true",{expires:1});
        window.location = "http://m.etradesupply.com";
        
    });
});
      
```

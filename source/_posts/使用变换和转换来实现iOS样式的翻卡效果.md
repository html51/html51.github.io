title: 使用变换和转换来实现iOS样式的翻卡效果
date: 2016-03-03 18:50:45
categories:
- CSS3
tags: [JavaScript,HTML5,CSS3]

-------
> 在网页中使用那些原生应用里的动画效果会让用户感到神奇。本实例向你展示了如何使用CSS重新实现那些常见的iOS动画。


### html
``` javascript
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8">
	<title>使用变换和转换来实现iOS样式的翻卡效果</title>

</head>

<body>
<div class="viewPort">
    <div id="card" class="card flipped">
        <div class="frontView">HTML51 Niles</div>
        <div class="backView">Hello!</div>
    </div>
</div>  
</body>
</html>
```
<!-- more -->

### css
``` javascript
.viewPort{
    width:200px;
    height: 260px;
    position: relative;
    margin: 0 auto 40px;
    border: 1px solid #ccc;
    -webkit-perspective: 800px;
    -moz-perspective: 800px;
    -ms-perspective: 800px;
    perspective: 800px;
}
.card{
    width:100%;
    height: 100%;
    position: absolute;
    -webkit-transition: transform 1s;
    -o-transition: transform 1s;
    transition: transform 1s;
    -webkit-transform-style: preserve-3d;
    -moz-transform-style: preserve-3d;
    -ms-transform-style: preserve-3d;
    transform-style: preserve-3d;
    -webkit-transform-origin:right center;
    -moz-transform-origin:right center;
    -ms-transform-origin:right center;
    -o-transform-origin:right center;
    transform-origin:right center;
}
.card.flipped{
    -webkit-transform: translateX(-100%) rotateY(-180deg);
    -ms-transform: translateX(-100%) rotateY(-180deg);
    -o-transform: translateX(-100%) rotateY(-180deg);
    transform: translateX(-100%) rotateY(-180deg);
}
.card .frontView,
.card .backView{
    height:100%;
    width:100%;
    background: black;
    line-height: 260px;
    color:white;
    text-align: center;
    font-weight: bold;
    font-size: 5em;
    position: absolute;
    -webkit-backface-visibility: hidden;
    -moz-backface-visibility: hidden;
    -ms-backface-visibility: hidden;
    backface-visibility: hidden;
}
.card .backView{
    -webkit-transform: rotateY(180deg);
    -ms-transform: rotateY(180deg);
    -o-transform: rotateY(180deg);
    transform: rotateY(180deg);
}
```
### js
``` javascript
document.querySelector('.viewPort').addEventListener('click', function(){
    var elem = document.querySelector('.card');
    elem.className = (elem.className == 'card') ? 'card flipped' : 'card';
}, false);
```

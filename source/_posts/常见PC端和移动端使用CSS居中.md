title: 常见PC端和移动端使用CSS居中
date: 2015-12-01 00:02:45
categories:
- CSS3
tags: [绝对居中,css3,移动]
---
#### **1.使用负margin值来进行居中**
> 此方法特别适合PC端，例如简单的弹出层。一般设置固定的宽度和高度，然后配合一半大小的负margin值，另外还需要left:50%，top:50%，这样就可以在页面居中啦~

#### **html**
``` javascript
<div class="container">
  <div class="box-center box-absolute">
    <h4 class="title">使用负margin值来进行居中</h4>
    <p>此方法特别适合PC端，一般设置固定的宽度和高度，然后配合一半大小的负margin值，另外还需要left:50%，top:50%，这样就可以在页面居中啦~</p>
  </div>
</div>
```
#### **css**
``` javascript
.container{
  background: #eee;
  color: #4fa46b;
  width: 100%;
  height: 400px;
  margin: 20px auto 40px;
  position:relative;
}
.box-center.box-absolute{
  width: 300px;
  height: 200px;
  padding: 20px;
  position: absolute;
  top: 50%;
  left: 50%;
  margin-left: -170px;
  /* (width + padding)/2 */
  margin-top: -120px;
  /* (height + padding)/2 */
}
.container .box-center{
  background: #BBB;
}
.box-center .title {
  padding: 0;
  margin: 0 0 .5em;
  line-height: 1em;
}
.box-center{
  color:#fff;
}
```
<!-- more -->

#### **2.使用inline-block方法**
> 貌似查看相关资料，借助:after伪类来实现。

#### **html**
``` javascript
<div class="container box-inline">
  <div class="box-center">
    <h4 class="title">使用inline-block值来进行居中</h4>
    <p>主要是借助:after伪类来实现，还是蛮不错的~~</p>
  </div>
</div>
```
#### **css**
``` javascript
.container{
  background: #eee;
  color: #4fa46b;
  width: 100%;
  height: 400px;
  margin: 20px auto 40px;
  position:relative;
}
.container.box-inline{
  text-align: center;
  overflow: auto;
}
.container .box-center{
  background: #BBB;
}
.box-center .title {
  padding: 0;
  margin: 0 0 .5em;
  line-height: 1em;
}
.box-center{
  color:#fff;
  padding: 20px;
}
.box-inline .box-center {
  text-align: left;
  max-width: 80%;
  /* max-width: calc(100% - 0.25em) /* Only for IE9+ */
}
.container.box-inline:after,
.box-inline .box-center {
  display: inline-block;
  vertical-align: middle;
}
.container.box-inline:after {
  content: ' ';
  height: 100%;
  margin-left: -0.25em;
  /* to offset spacing. may vary with fonts */
}
```
#### **3.flexbox方法**
> 该方法运用到移动端兼容性还是蛮好的，就让我们学习一下新属性是如何用的吧~

#### **html**
``` javascript
<div class="container box-flexbox">
  <div class="box-center">
    <h4 class="title">使用flexbox来进行居中</h4>
    <p>该方法运用到移动端兼容性还是蛮好的，就让我们学习一下新属性是如何用的吧~</p>
  </div>
</div>
```
#### **css**
```javascript
.container{
  background: #eee;
  color: #4fa46b;
  width: 100%;
  height: 400px;
  margin: 20px auto 40px;
  position:relative;
}
.container.box-flexbox{
  display: -webkit-box;
  display: -moz-box;
  display: -ms-flexbox;
  display: -webkit-flex;
  display: flex;
  -webkit-box-align: center;
  -moz-box-align: center;
  -ms-flex-align: center;
  -webkit-align-items: center;
  align-items: center;
  -webkit-box-pack: center;
  -moz-box-pack: center;
  -ms-flex-pack: center;
  -webkit-justify-content: center;
  justify-content: center;
}
.container .box-center{
  background: #BBB;
}
.box-center .title {
  padding: 0;
  margin: 0 0 .5em;
  line-height: 1em;
}
.box-center{
  color:#fff;
  padding: 20px;
}
```
#### **4.transform方法**
> css3新属性，移动端兼容也蛮不错，主要translate的负值和定位结合使用。

#### **html**
``` javascript
<div class="container">
  <div class="box-center box-translated">
    <h4 class="title">使用transform来进行居中</h4>
    <p>css3新属性，移动端兼容也蛮不错，主要translate的负值和定位结合使用。</p>
  </div>
</div>
```
#### **css**
```javascript
.container{
  background: #eee;
  color: #4fa46b;
  width: 100%;
  height: 400px;
  margin: 20px auto 40px;
  position:relative;
}
.box-translated {
  width: 50%;
  margin: auto;
  position: absolute;
  top: 50%;
  left: 50%;
  -webkit-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
}
.container .box-center{
  background: #BBB;
}
.box-center .title {
  padding: 0;
  margin: 0 0 .5em;
  line-height: 1em;
}
.box-center{
  color:#fff;
  padding: 20px;
}
```
#### **5.使用绝对值absolute方法**
> 这种方法根据绝对值相应的值设置为0，然后在使用margin:auto，特别适合移动到。

#### **html**
``` javascript
<div class="container">
  <div class="box-center box-absolute">
    <h4 class="title">使用绝对值absolute方法</h4>
    <p>这种方法根据绝对值相应的值设置为0，然后在使用margin:auto，特别适合移动到。</p>
  </div>
</div>
```
#### **css**
``` javascript
.container{
  background: #eee;
  color: #4fa46b;
  width: 100%;
  height: 400px;
  margin: 20px auto 40px;
  position:relative;
}
.box-absolute{
  height: 50%;
  width: 50%;
  overflow: auto;
  margin: auto;
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
}
.container .box-center{
  background: #BBB;
}
.box-center .title {
  padding: 0;
  margin: 0 0 .5em;
  line-height: 1em;
}
.box-center{
  color:#fff;
  padding: 20px;
}
```

#### **6.table-cell方法**
> 这个方法类似与table，以表格单元格的形式呈现

#### **html**
``` javascript
<div class="container box-table">
  <div class="box-tablecell">
      <div class="box-center">
        <h4 class="title">使用table-cell方法来进行居中</h4>
        <p>这个方法类似与table，以表格单元格的形式呈现。</p>
      </div>
  </div>
</div>
```
#### **css**
``` javascript
.container{
  background: #eee;
  color: #4fa46b;
  width: 100%;
  height: 400px;
  margin: 20px auto 40px;
  position:relative;
}
.container.box-table {
  display: table;
}
.box-table .box-tablecell {
  display: table-cell;
  vertical-align: middle;
}
.box-table .box-center {
  width: 50%;
  margin: 0 auto;
}
.container .box-center{
  background: #BBB;
}
.box-center .title {
  padding: 0;
  margin: 0 0 .5em;
  line-height: 1em;
}
.box-center{
  color:#fff;
  padding: 20px;
}

```
------
参考资料：
http://codepen.io/shshaw/full/gEiDt

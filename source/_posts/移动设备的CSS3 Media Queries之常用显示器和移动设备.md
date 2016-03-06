title: 移动设备的CSS3 Media Queries之常用显示器和移动设备
date: 2015-12-15 21:50:45
categories:
- CSS3
tags: [Media Queries,css3,HTC One,BlackBerry,Sony,ASUS,Kindle,ViewSonic]
---

> 随着Web响应式的趋势越来越流行，媒体查询在创建响应式网站中起到了主要作用。利用媒体查询，我们可以针对不同的设备，如显示器、智能手机和平板，来写CSS。在这里我把常用的媒体查询进行了分类总结，希望在以后的工作当中方便查阅。这篇主要是对常用显示器和移动设备进行了总结。

### 显示器媒体查询

#### **640px**
``` javascript
@media screen and (max-width: 640px) { 

}
```
#### **800px**
``` javascript
@media screen and (max-width: 800px) {

}
```
#### **1024px**
``` javascript
@media screen and (max-width: 1024px) { 

}
```

#### **HTC Evo，BlackBerry Torch，HTC Thunderbolt，HD2**
```
@media screen and (max-device-width: 480px) 
{ 

}
```
### 平板媒体查询

#### **Motorola Xoom**
```
/* Landscape Mode */
@media (max-device-width: 1280px) and (orientation: landscape) 
{ 

}

/* Portrait Mode */
@media (max-device-width: 800px) and (orientation: portrait) 
{ 

}
```
#### **HTC Flyer**
```
/* Landscape Mode */
@media (max-device-width: 1024px) and (orientation: landscape) 
{ 

}

/* Portrait Mode */
@media (max-device-width: 600px) and (orientation: portrait) 
{ 

}
```
<!-- more -->

#### **BlackBerry PlayBook**
```
/* Landscape Mode */
@media (max-device-width: 1024px) and (orientation: landscape) 
{ 

}

/* Portrait Mode */
@media (max-device-width: 600px) and (orientation: portrait) 
{ 

}
```
#### **HP TouchPad**
```
/* Landscape Mode */
@media (max-device-width: 1024px) and (orientation: landscape) 
{ 

}

/* Portrait Mode */
@media (max-device-width: 768px) and (orientation: portrait) 
{ 

}
```
#### **Lenovo Thinkpad Tablet**
```
/* Landscape Mode */
@media (max-device-width: 1280px) and (orientation: landscape) 
{ 

}

/* Portrait Mode */
@media (max-device-width: 800px) and (orientation: portrait) 
{ 

}
```
#### **Sony Tablet S**
```
/* Landscape Mode */
@media (max-device-width: 1280px) and (orientation: landscape) 
{ 

}

/* Portrait Mode */
@media (max-device-width: 800px) and (orientation: portrait) 
{ 

}
```
#### **T-Mobile G-Slate**
```
/* Landscape Mode */
@media (max-device-width: 1280px) and (orientation: landscape) 
{ 

}

/* Portrait Mode */
@media (max-device-width: 768px) and (orientation: portrait) 
{ 

}
```
#### **ViewSonic ViewPad 10**
```
/* Landscape Mode */
@media (max-device-width: 1024px) and (orientation: landscape) 
{ 

}

/* Portrait Mode */
@media (max-device-width: 600px) and (orientation: portrait) 
{ 

}
```
#### **Dell Streak 7**
```
/* Landscape Mode */
@media (max-device-width: 800px) and (orientation: landscape) 
{ 

}

/* Portrait Mode */
@media (max-device-width: 480px) and (orientation: portrait) 
{ 

}
```
#### **ASUS Eee Pad Transformer**
```
/* Landscape Mode */
@media (max-device-width: 1080px) and (orientation: landscape) 
{ 

}

/* Portrait Mode */
@media (max-device-width: 800px) and (orientation: portrait) 
{ 

}
```

#### **HTC One landscape & portrait**
```
@media screen
and (device-width: 360px)
and (device-height: 640px)
and (-webkit-device-pixel-ratio: 3) {

}
```
#### **HTC One portrait**
```
@media screen
and (device-width: 360px)
and (device-height: 640px)
and (-webkit-device-pixel-ratio: 3)
and (orientation: portrait) {

}
```
#### **HTC One landscape**
```
@media screen
and (device-width: 360px)
and (device-height: 640px)
and (-webkit-device-pixel-ratio: 3)
and (orientation: landscape) {

}
```

#### **Asus Nexus 7 landscape & portrait**
```
@media screen
and (device-width: 601px)
and (device-height: 906px)
and (-webkit-min-device-pixel-ratio: 1.331)
and (-webkit-max-device-pixel-ratio: 1.332) {

}
```
#### **Asus Nexus 7 portrait**
```
@media screen
and (device-width: 601px)
and (device-height: 906px)
and (-webkit-min-device-pixel-ratio: 1.331)
and (-webkit-max-device-pixel-ratio: 1.332)
and (orientation: portrait) {

}
```
#### **Asus Nexus 7 landscape**
```
@media screen
and (device-width: 601px)
and (device-height: 906px)
and (-webkit-min-device-pixel-ratio: 1.331)
and (-webkit-max-device-pixel-ratio: 1.332)
and (orientation: landscape) {

}

```
#### **Kindle Fire HD 7" landscape & portrait**
```
@media only screen
and (min-device-width: 800px)
and (max-device-width: 1280px)
and (-webkit-min-device-pixel-ratio: 1.5) {

}
```
#### **Kindle Fire HD 7" portrait**
```
@media only screen
and (min-device-width: 800px)
and (max-device-width: 1280px)
and (-webkit-min-device-pixel-ratio: 1.5)
and (orientation: portrait) {
}
```
#### **Kindle Fire HD 7" landscape**
```
@media only screen
and (min-device-width: 800px)
and (max-device-width: 1280px)
and (-webkit-min-device-pixel-ratio: 1.5)
and (orientation: landscape) {

}
```
#### **Kindle Fire HD 8.9" landscape & portrait**
```
@media only screen
and (min-device-width: 1200px)
and (max-device-width: 1600px)
and (-webkit-min-device-pixel-ratio: 1.5) {

}
```
#### **Kindle Fire HD 8.9" portrait**
```
@media only screen
and (min-device-width: 1200px)
and (max-device-width: 1600px)
and (-webkit-min-device-pixel-ratio: 1.5)
and (orientation: portrait) {
}
```
#### **Kindle Fire HD 8.9" landscape**
```
@media only screen
and (min-device-width: 1200px)
and (max-device-width: 1600px)
and (-webkit-min-device-pixel-ratio: 1.5)
and (orientation: landscape) {

}
```
#### **Non-Retina Screens**
```
@media screen
and (min-device-width: 1200px)
and (max-device-width: 1600px)
and (-webkit-min-device-pixel-ratio: 1) {
}

```
#### **Retina Screens**
```
@media screen
and (min-device-width: 1200px)
and (max-device-width: 1600px)
and (-webkit-min-device-pixel-ratio: 2)
and (min-resolution: 192dpi) {
}

```

#### **Moto 360 Watch**
```
@media
(max-device-width: 218px)
and (max-device-height: 281px) {

}
```
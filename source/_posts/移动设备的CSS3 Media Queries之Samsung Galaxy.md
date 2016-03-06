title: 移动设备的CSS3 Media Queries之Samsung Galaxy
date: 2015-12-12 21:32:45
categories:
- CSS3

tags: [Media Queries,css3,移动,Samsung Galaxy]
---

> 随着Web响应式的趋势越来越流行，媒体查询在创建响应式网站中起到了主要作用。利用媒体查询，我们可以针对不同的设备，如显示器、智能手机和平板，来写CSS。在这里我把常用的媒体查询进行了分类总结，希望在以后的工作当中方便查阅。这篇主要是对Samsung Galaxy进行了总结。

#### **Galaxy S3 landscape & portrait**
```
@media screen
and (device-width: 320px)
and (device-height: 640px)
and (-webkit-device-pixel-ratio: 2) {

}
```
#### **Galaxy S3 portrait**
```
@media screen
and (device-width: 320px)
and (device-height: 640px)
and (-webkit-device-pixel-ratio: 2)
and (orientation: portrait) {

}
```
#### **Galaxy S3 landscape**
```
@media screen
and (device-width: 320px)
and (device-height: 640px)
and (-webkit-device-pixel-ratio: 2)
and (orientation: landscape) {

}
```
<!-- more -->

#### **Galaxy S4 landscape & portrait**
```
@media screen
and (device-width: 320px)
and (device-height: 640px)
and (-webkit-device-pixel-ratio: 3) {

}
```
#### **Galaxy S4 portrait**
```
@media screen
and (device-width: 320px)
and (device-height: 640px)
and (-webkit-device-pixel-ratio: 3)
and (orientation: portrait) {

}
```
#### **Galaxy S4 landscape**
```
@media screen
and (device-width: 320px)
and (device-height: 640px)
and (-webkit-device-pixel-ratio: 3)
and (orientation: landscape) {

}
```
#### **Galaxy S5 landscape & portrait**
```
@media screen
and (device-width: 360px)
and (device-height: 640px)
and (-webkit-device-pixel-ratio: 3) {

}

```
#### **Galaxy S5 portrait**
```
@media screen
and (device-width: 360px)
and (device-height: 640px)
and (-webkit-device-pixel-ratio: 3)
and (orientation: portrait) {

}
```
#### **Galaxy S5 landscape**
```
@media screen
and (device-width: 360px)
and (device-height: 640px)
and (-webkit-device-pixel-ratio: 3)
and (orientation: landscape) {

}
```

#### **Galaxy Tab 10.1 landscape & portrait**
```
@media
(min-device-width: 800px)
and (max-device-width: 1280px) {

}
```
#### **Galaxy Tab 10.1 portrait**
```
@media
(max-device-width: 800px)
and (orientation: portrait) {

}

```
#### **Galaxy Tab 10.1 landscape**
```
@media
(max-device-width: 1280px)
and (orientation: landscape) {

}
```

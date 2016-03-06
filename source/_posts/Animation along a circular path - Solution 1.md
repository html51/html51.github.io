title: Animation along a circular path - Solution 1
date: 2016-01-21 22:03:45
categories:
- csssecrets
tags: [CSS3,csssecrets]

---

#### **HTML**
``` html
<div class="path">
	<div class="avatar">
		<img src="http://lea.verou.me/book/adamcatlace.jpg" />
	</div>
</div>
```
<!-- more -->

#### **CSS**
``` css
/**
 * Animation along a circular path - Solution 1
 */
 
@keyframes spin {
	to { transform: rotate(1turn); }
}

.avatar {
	animation: spin 3s infinite linear;
	transform-origin: 50% 150px;
}

.avatar > img {
	animation: inherit;
	animation-direction: reverse;
}

/* Anything below this is just styling */

.avatar {
	width: 50px;
	margin: 0 auto;
	border-radius: 50%;
	overflow: hidden;
}

.avatar > img {
	display: block;
	width: inherit;
}

.path {
	width: 300px; height: 300px;
	padding: 20px;
	border-radius: 50%;
	background: #fb3;
}
```





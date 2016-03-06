title: Adjusting tabs
date: 2016-01-20 21:03:45
categories:
- csssecrets
tags: [CSS3,csssecrets]

---

#### **HTML**
``` html
<pre><code>// Default tab size
while (true) {
	var d = new Date();
	if (d.getDate()==1 &amp;&amp;
	    d.getMonth()==3) {
		alert("TROLOLOL");
	}
}</code></pre>

<pre><code>// tab-size: 2;
while (true) {
	var d = new Date();
	if (d.getDate()==1 &amp;&amp;
	    d.getMonth()==3) {
		alert("TROLOLOL");
	}
}</code></pre>

<pre><code>// tab-size: 4;
while (true) {
	var d = new Date();
	if (d.getDate()==1 &amp;&amp;
	    d.getMonth()==3) {
		alert("TROLOLOL");
	}
}</code></pre>

<pre><code>// tab-size: 0;
while (true) {
	var d = new Date();
	if (d.getDate()==1 &amp;&amp;
	    d.getMonth()==3) {
		alert("TROLOLOL");
	}
}</code></pre>
```
<!-- more -->

#### **CSS**
``` css
/**
 * Adjusting tabs
 */

pre { 
	padding: .5em;
	line-height: 1.5;
	background: hsl(20, 50%, 95%);
	font-family: Consolas, Monaco, monospace;
}

pre:nth-of-type(2) { tab-size: 2 }
pre:nth-of-type(3) { tab-size: 4 }
pre:nth-of-type(4) { tab-size: 0 }

code {
	font: inherit;
}
```





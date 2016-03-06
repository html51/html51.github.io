title: Ctrl+Enter提交留言
date: 2016-01-03 23:02:45
categories:
- JavaScript
tags: [JavaScript,提交留言]


-------

> 任何东西的发表功能，都想有个 Ctrl+Enter 的快捷键，这里总结一下。

#### **html**
``` javascript
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Ctrl+Enter提交留言</title>
</head>
<body>
		
<script type="text/javascript">
	loadCommentShortcut('commentform', 'submit_comment', ' (Ctrl+Enter)');
</script>

</body>
</html>
```
<!-- more -->

#### **javascript**
``` javascript
function loadCommentShortcut(frm, submitbnt, desc) {
    document.getElementById(frm).onkeydown = function (moz_ev) {
        var ev = null;
        ev = window.event ? window.event : moz_ev;
        if (ev != null && ev.ctrlKey && ev.keyCode == 13) {
            document.getElementById(submitbnt).click();
        }
    };
    document.getElementById(submitbnt).value += desc;
}
```

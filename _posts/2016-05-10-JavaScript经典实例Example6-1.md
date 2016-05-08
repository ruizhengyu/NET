---
date: 2016-05-10 12:54:30+00:00
layout: post
title: JavaScript经典实例 示例6-1
categories: JavaScript经典实例
tags:  JavaScript  JavaScript经典实例
---

标量参数和数组参数的功能性区别
----------------

<html xmlns = "http://www.w3.org/1999/xhtml">
<head>
<title>Function test</title>
<script type="text/javascript">
//<![CDATA

window.onload = function(){
    var items = new Array('apple', 'orange', 'cherry', 'lime');
    var sep = '*';
    concatenateString(items, sep);
    
    alert(items);
    alert(sep);
}

function concatenateString(strings, separator){
    var result = "";
    for(var i = 0; i < strings.length; i++){
        result += strings[i] + separator;
    }
    
    //将result赋值给separator
    separator = result;
    
    //和数组
    strings[strings.length] = result;
}

//--><!]]>
</script>
</head>
<body>
</body>
</html>

源码如下：

``` javascript
<!DOCTYPE html>
<html xmlns = "http://www.w3.org/1999/xhtml">
<head>
<title>Function test</title>
<script type="text/javascript">
//<![CDATA

window.onload = function(){
    var items = new Array('apple', 'orange', 'cherry', 'lime');
    var sep = '*';
    concatenateString(items, sep);
    
    alert(items);
    alert(sep);
}

function concatenateString(strings, separator){
    var result = "";
    for(var i = 0; i < strings.length; i++){
        result += strings[i] + separator;
    }
    
    //将result赋值给separator
    separator = result;
    
    //和数组
    strings[strings.length] = result;
}

//--><!]]>
</script>
</head>
<body>
</body>
</html>
``` 
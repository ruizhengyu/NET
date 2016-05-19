---
date: 2016-03-21 14:26:30+00:00
layout: post
title: JavaScript经典实例 示例10-1
categories: JavaScript经典实例
tags:  JavaScript  JavaScript经典实例
---

如果脚本关闭的话，表单元素默认地设置为隐藏，如果支持脚本的话，则会显示
----------------

<html xmlns="http://www.w3.org/1999/xthml">
<head>
<title>Populating Selection Lists</title>
<script>
//<![CDTAT[

var citystore = new Array();
citystore[0] = ['CA', 'San Francisco'];
citystore[1] = ['CA', 'Los Angeles'];
citystore[2] = ['CA', 'San Diego'];
citystore[3] = ['MO', 'St. louis'];
citystore[4] = ['MO', 'Kansas City'];
citystore[5] = ['WA', 'Seattle'];
citystore[6] = ['WA', 'Spokane'];
citystore[7] = ['WA', 'Redmond'];

window.onload = function(){
    document.getElementById("state").onchange = filterCities;
}

function filterCities(){
    var state = this.value;
    var city = document.getElementById("cities");
    city.options.length = 0;
    
    for(var i = 0; i < citystore.length; i++){
        var st = citystore[i][0];
        if(st == state){
            var opt = new Option(citystore[i][1]);
            try{
                city.add(opt, null);
            }catch(e){
                city.add(opt);
            }
        }
    }
}

//--><!]]>
</script>
</head>
<body>
<form id="picker" method="post" action="">
Group 1:<input type="radio" name="group1" value="one"/><br />
Group 2:<input type="radio" name="group1" value="two"/><br />
Group 3:<input type="radio" name="group1" value="three"/><br />
<br />
<div id="hidden_elements">
Input 1:<input type="text" id="intext" />
Input 2:<input type="text" id="intext2" />
Input 3:<input type="text" id="intext3" /><br /><br />
</div>
<input type="submit" id="submitbutton" value="Send form" />
</form>
</body>
</html>

源码如下：

``` javascript
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xthml">
<head>
<title>Populating Selection Lists</title>
<script>
//<![CDTAT[

var citystore = new Array();
citystore[0] = ['CA', 'San Francisco'];
citystore[1] = ['CA', 'Los Angeles'];
citystore[2] = ['CA', 'San Diego'];
citystore[3] = ['MO', 'St. louis'];
citystore[4] = ['MO', 'Kansas City'];
citystore[5] = ['WA', 'Seattle'];
citystore[6] = ['WA', 'Spokane'];
citystore[7] = ['WA', 'Redmond'];

window.onload = function(){
    document.getElementById("state").onchange = filterCities;
}

function filterCities(){
    var state = this.value;
    var city = document.getElementById("cities");
    city.options.length = 0;
    
    for(var i = 0; i < citystore.length; i++){
        var st = citystore[i][0];
        if(st == state){
            var opt = new Option(citystore[i][1]);
            try{
                city.add(opt, null);
            }catch(e){
                city.add(opt);
            }
        }
    }
}

//--><!]]>
</script>
</head>
<body>
<form id="picker" method="post" action="">
Group 1:<input type="radio" name="group1" value="one"/><br />
Group 2:<input type="radio" name="group1" value="two"/><br />
Group 3:<input type="radio" name="group1" value="three"/><br />
<br />
<div id="hidden_elements">
Input 1:<input type="text" id="intext" />
Input 2:<input type="text" id="intext2" />
Input 3:<input type="text" id="intext3" /><br /><br />
</div>
<input type="submit" id="submitbutton" value="Send form" />
</form>
</body>
</html>
``` 

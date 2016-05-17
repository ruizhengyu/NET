---
date: 2016-05-23 16:26:30+00:00
layout: post
title: JavaScript经典实例 示例11-2
categories: JavaScript经典实例
tags:  JavaScript  JavaScript经典实例
---

展示getElementsByTagName和NodeList动态集合属性
----------------

<html xmlns="http://www.w3.org/1999/xthml" xml:lang="en">
<head>
<title>Namespace</title>
<script type="text/javascript">
//<![CDTAT[

window.onload = function(){

    var str = "";
    var title = document.getElementsByTagName("title");
    for(var i = 0; i < title.length; i++){
        str += title.item(i).namespaceURI + " " + title.item(i).prefix + " " + title.item(i).localName + " " + title.item(i).text + " ";
    }
    var blk1 = document.getElementById("result1");
    blk1.innerHTML = str;
    
    str = "";
    if(!document.getElementsByTagNameNS){
        return;
    }
    var titlens = document.getElementsByTagNameNS("http://purl.org/dc/element/1.1/", "title");
    for(var i = 0; i < titlens.length; i++){
        str += titlens.item(i).namespaceURI + " " + titlens.item(i).prefix + " " + titlens.item(i).localName + " " + titlens.item(i).textContent + " ";
    }
    var blk2 = document.getElementById("result2");
    blk2.innerHTML = str;
}

//--><!]]>
</script>
</head>
<body>
<h1>SVG</h1>
<svg id="svgelem" height="800" xmlns="http://www.w3.org/2000/svg">
    <circle id="redcircle" cx="300" cy="300" r="300" fill="red" />
    <metadata>
        <rdf:RDF xmlns:cc="http://web.resource.org/cc/" xmlns:dc="http://purl.org/dc/element/1.1/" xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#">
            <cc:Work rdf:about="">
                <dc:title>Sizing Red Circle</dc:title>
                <dc:description></dc:description>
                <dc:subject>
                    <rdf:Bag>
                        <rdf:li>circle</rdf:li>
                        <rdf:li>red</rdf:li>
                        <rdf:li>graphic</rdf:li>
                    </rdf:Bag>
                </dc:subject>
                <dc:publisher>
                    <cc:Agent rdf:about="http://www.openclipart.org">
                        <dc:title>Testing RDF in SVG</dc:title>
                    </cc:Agent>
                </dc:publisher>
                <dc:creator>
                    <cc:Agent>
                        <dc:title id="title">Testing</dc:title>
                    </cc:Agent>
                </dc:creator>
                <dc:rights>
                    <cc:Agent>
                        <dc:title>Testing</dc:title>
                    </cc:Agent>
                </dc:rights>
                <dc:date></dc:date>
                <dc:format>image/svg+xml</dc:format>
                <dc:type rdf:resource="http://purl.org/dc/dcmitype/StillImage" />
                <cc:license rdf:resource="http://web.resource.org/cc/PublicDomain" />
                <dc:language>en</dc:language>
            </cc:Work>
            <cc:License rdf:about="http://web.resource.org/cc/PublicDomain">
                <cc:permits rdf:resource="http://web.resource.org/cc/Reproduction" />
                <cc:permits rdf:resource="http://web.resource.org/cc/Distribution" />
                <cc:permits rdf:resource="http://web.resource.org/cc/DerivativeWorks" />
            </cc:License>
        </rdf:RDF>
    </metadata>
</svg>
<div id="result1"></div>
<div id="result2"></div>
</body>
</html>

源码如下：

``` javascript
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.1 plus MathML 2.0 plus SVG 1.1//EN" "http://www.w3.org/2002/04/xhtml-math-svg/xhtml-math-svg.dtd">
<html xmlns="http://www.w3.org/1999/xthml" xml:lang="en">
<head>
<title>Namespace</title>
<script type="text/javascript">
//<![CDTAT[

window.onload = function(){

    var str = "";
    var title = document.getElementsByTagName("title");
    for(var i = 0; i < title.length; i++){
        str += title.item(i).namespaceURI + " " + title.item(i).prefix + " " + title.item(i).localName + " " + title.item(i).text + " ";
    }
    alert(str);
    
    str = "";
    if(!document.getElementsByTagNameNS){
        return;
    }
    var titlens = document.getElementsByTagNameNS("http://purl.org/dc/element/1.1/", "title");
    for(var i = 0; i < titlens.length; i++){
        str += titlens.item(i).namespaceURI + " " + titlens.item(i).prefix + " " + titlens.item(i).localName + " " + titlens.item(i).textContent + " ";
    }
    alert(str);
}

//--><!]]>
</script>
</head>
<body>
<h1>SVG</h1>
<svg id="svgelem" height="800" xmlns="http://www.w3.org/2000/svg">
    <circle id="redcircle" cx="300" cy="300" r="300" fill="red" />
    <metadata>
        <rdf:RDF xmlns:cc="http://web.resource.org/cc/" xmlns:dc="http://purl.org/dc/element/1.1/" xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#">
            <cc:Work rdf:about="">
                <dc:title>Sizing Red Circle</dc:title>
                <dc:description></dc:description>
                <dc:subject>
                    <rdf:Bag>
                        <rdf:li>circle</rdf:li>
                        <rdf:li>red</rdf:li>
                        <rdf:li>graphic</rdf:li>
                    </rdf:Bag>
                </dc:subject>
                <dc:publisher>
                    <cc:Agent rdf:about="http://www.openclipart.org">
                        <dc:title>Testing RDF in SVG</dc:title>
                    </cc:Agent>
                </dc:publisher>
                <dc:creator>
                    <cc:Agent>
                        <dc:title id="title">Testing</dc:title>
                    </cc:Agent>
                </dc:creator>
                <dc:rights>
                    <cc:Agent>
                        <dc:title>Testing</dc:title>
                    </cc:Agent>
                </dc:rights>
                <dc:date></dc:date>
                <dc:format>image/svg+xml</dc:format>
                <dc:type rdf:resource="http://purl.org/dc/dcmitype/StillImage" />
                <cc:license rdf:resource="http://web.resource.org/cc/PublicDomain" />
                <dc:language>en</dc:language>
            </cc:Work>
            <cc:License rdf:about="http://web.resource.org/cc/PublicDomain">
                <cc:permits rdf:resource="http://web.resource.org/cc/Reproduction" />
                <cc:permits rdf:resource="http://web.resource.org/cc/Distribution" />
                <cc:permits rdf:resource="http://web.resource.org/cc/DerivativeWorks" />
            </cc:License>
        </rdf:RDF>
    </metadata>
</svg>
</body>
</html>
``` 

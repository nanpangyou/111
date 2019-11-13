---
layout: learnnote
title: css属性
date: 2019-11-13 18:12:29
tags:
---

# 遇见的，不会的，CSS 属性

1. backface-visibility

   功能： 隐藏被旋转的 div 元素的背面

   ```
   <style>
   div
   {
   position:relative;
   height:60px;
   width:60px;
   border:1px solid #000;
   background-color:yellow;
   transform:rotateY(180deg);
   -webkit-transform:rotateY(180deg); /* Chrome and Safari */
   -moz-transform:rotateY(180deg); /* Firefox */
   }
   #div1
   {
   -webkit-backface-visibility:hidden;
   -moz-backface-visibility:hidden;
   -ms-backface-visibility:hidden;
   }
   #div2
   {
   -webkit-backface-visibility:visible;
   -moz-backface-visibility:visible;
   -ms-backface-visibility:visible;
   }
   </style>
   </head>
   <body>

   <p>本例有两个 div 元素，均旋转 180 度，背向用户。</p>

   <p>第一个 div 元素的 backface-visibility 属性设置为 "hidden"，所以应该是不可见的。</p>

   <div id="div1">DIV 1</div>

   <div id="div2">DIV 2</div>

   ```

   [can i use](https://www.caniuse.com/#search=backface-visibility)

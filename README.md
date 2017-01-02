# jQuery轮播器插件

## 一、运行示例

双击index.html文件查看示例效果。

## 二、用法Usage

**详细代码见文件夹jqCarousel**

1. index.html文件代码

   ```html
   <!DOCTYPE html>
   <html lang="zh-CN">
     <head>
       <meta charset="utf-8">
       <meta http-equiv="X-UA-Compatible" content="IE=edge">
       <meta name="viewport" content="width=device-width, initial-scale=1">
       <title>jQuery轮播插件</title>
       <script type="text/javascript" src="jquery-1.10.1.js"></script>
       <script type="text/javascript" src="jquery.carousel.js"></script>
       <script type="text/javascript" src="index.js"></script>
       <style type="text/css">
          .divStyle{
             text-align: center;
             color: #fff;
             font-size: 20px;
             line-height: 250px;
          }
       </style>
     </head>
     <body>
       <p>水平方向右滑动轮播：slidex-right</p>
       <div class="a">
           <img class="item" src="images/banner1.jpg">
           <img class="item" src="images/banner2.jpg">
           <img class="item" src="images/banner3.jpg"> 
       </div>
       <p>水平方向左滑动轮播：slidex-left</p>
       <div class="b">
           <img class="item" src="images/banner1.jpg">
           <img class="item" src="images/banner2.jpg">
           <img class="item" src="images/banner3.jpg"> 
       </div>     
       <p>垂直方向下滑动轮播：slidey-down</p>
       <div class="c">
            <img class="item" src="images/jd1.jpg">
            <img class="item" src="images/jd2.jpg">
            <img class="item" src="images/jd3.jpg">
            <img class="item" src="images/jd4.jpg">
            <img class="item" src="images/jd5.jpg">
            <img class="item" src="images/jd6.jpg">
       </div>
       <p>垂直方向上滑动轮播：slidey-up</p>
       <div class="d">
            <img class="item" src="images/jd1.jpg">
            <img class="item" src="images/jd2.jpg">
            <img class="item" src="images/jd3.jpg">
            <img class="item" src="images/jd4.jpg">
            <img class="item" src="images/jd5.jpg">
            <img class="item" src="images/jd6.jpg">
       </div>    
       <p>水平方向渐隐轮播：opacx</p>
       <div class="e">
            <div class="item divStyle" style="background:red">1</div>
            <div class="item divStyle" style="background:blue">2</div>
            <div class="item divStyle" style="background:green">3</div>
            <div class="item divStyle" style="background:orange">4</div>
            <div class="item divStyle" style="background:yellow">5</div>
            <div class="item divStyle" style="background:maroon">6</div>
            <div class="item divStyle" style="background:gray">7</div>
            <div class="item divStyle" style="background:purple">8</div>
            <div class="item divStyle" style="background:black">9</div>
       </div>
       <p>垂直方向渐隐轮播：opacy</p>
       <div class="f">
            <div class="item divStyle" style="background:red">1</div>
            <div class="item divStyle" style="background:blue">2</div>
            <div class="item divStyle" style="background:green">3</div>
            <div class="item divStyle" style="background:orange">4</div>
            <div class="item divStyle" style="background:yellow">5</div>
            <div class="item divStyle" style="background:maroon">6</div>
            <div class="item divStyle" style="background:gray">7</div>
            <div class="item divStyle" style="background:purple">8</div>
            <div class="item divStyle" style="background:black">9</div>
       </div>
     </body>
   </html>
   ```

   **PS：**

   * 在head区域引入jquery文件，jquery.carousel.js轮播器插件文件，index.js文件。
   * 以父元素div包裹一系列子元素，内层子元素为需要轮播的元素，给子元素都加上class="item"的类名。
   * 示例一共有六种不同的轮播器轮播效果，运行示例可以看到。

2. index.js文件代码

   ```
   $(function(){      
      //水平方向右滑动轮播
      $('.a').jCarousel({
         type:'slidex-right',
         carsize: {carwidth:700,carheight:150},
      });
      //水平方向左滑动轮播
      $('.b').jCarousel({
         type:'slidex-left',
         carsize: {carwidth:700,carheight:150},
      });       
      //垂直方向下滑动轮播
      $('.c').jCarousel({
         type:'slidey-down',
         carsize: {carwidth:600,carheight:400},
      });
      //垂直方向上滑动轮播
      $('.d').jCarousel({
         type:'slidey-up',
         carsize: {carwidth:600,carheight:400},
      });       
      //水平方向渐隐轮播
      $('.e').jCarousel({
         type:'opacx',
         carsize: {carwidth:500,carheight:300},
      });
      //垂直方向渐隐轮播
      $('.f').jCarousel({
         type:'opacy',
         carsize: {carwidth:500,carheight:300},
      });
   });
   ```

   **PS：**

   * 在调用时，选中父元素标签，调用jCarousel方法即可，参数传递一个对象，用来配置轮播器，详细参数配置见下文。如：$(parent).jCarousel({ });

   ## 三、API

   1. jQuery轮播器插件参数配置

      * type:       配置轮播器的轮播类型，是一个字符串，有六个选择类型：

        ​                slidex-left：    水平方向 左滑动；

        ​                slidex-right： 水平方向 右滑动；

        ​                slidey-up：     垂直方向 上滑动；

        ​                slidey-down：垂直方向 下滑动；

        ​                opacx：           水平方向 渐隐；

        ​                opacy：           垂直方向渐隐；

      * auto:       配置自动轮播，是一个对象，包括：

        ​                isauto:   配置是否自动轮播，是一个布尔值，true表示自动轮播，false表示禁止自动轮播；

        ​                interval: 配置自动轮播间隔时间，是一个数值，默认单位为‘ms’；

      * istouch:  配置是否支持鼠标拖动轮播，是一个布尔值，true表示支持，false表示不支持；

      * circle:      配置轮播器下方小圆点，是一个对象，包括：

        ​                isshow:  配置是否显示下方小圆点，是一个布尔值，true表示显示，false表示不显示；

        ​                cird:       配置小圆点的直径大小，是一个数值，默认单位是‘px’；

      * arrow:    配置轮播器的箭头，是一个对象，包括：

        ​                isshow:       配置是否显示箭头，是一个布尔值，true表示显示，false表示不显示；

        ​                arrowsize:  配置箭头的大小，是一个数值，默认单位为‘px’；

      * carsize:  配置轮播器的尺寸，是一个对象，包括：

        ​                carwidth:    配置轮播器的宽度，是一个数值，默认单位为‘px’；

        ​                carheight：配置轮播器的高度，是一个数值，默认单位为‘px’；

      * onchanging:  配置执行完轮播后的回调函数，是一个方法。

   2. jQuery轮播器插件默认参数配置

      以下为轮播器插件的默认配置，在调用时可根据需要更改默认配置，也可以通过传递参数覆盖默认配置；

          {
             type: 'slidex-right',
             auto: {isauto:true,interval:2000},
             istouch:true,  
             circle: {isshow:true,cird:15},
             arrow: {isshow:true,arrowsize:24},
             carsize: {carwidth:750,carheight:450},
             onchanging: function(){}
          }








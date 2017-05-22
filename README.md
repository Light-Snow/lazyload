## lazyload
延迟加载图片插件
jquery.lazyload.js 是一个用 JavaScript 编写的jQuery 插件. 它可以延迟加载长页面中的图片. 在浏览器可视区域外的图片不会被载入,
直到用户将页面滚动到它们所在的位置.这与图片预加载的处理方式正好是相反的.
在包含很多大图片长页面中延迟加载图片可以加快页面加载速度.浏览器将会在加载可见图片之后即进入就绪状态. 在某些情况下还可以帮助降低服务器负担. 


## 使用
```
<script type="text/javascript" src="jquery-1.11.1.min.js"></script>
<script type="text/javascript" src="jquery.lazyload.min.js"></script>
```

```
<ul>
	<li>
		<img class="lazy loading"   data-original="img/1.jpg">
	</li>
	<li>
		<img class="lazy loading"  data-original="img/2.jpg">
	</li>
	<li>
		<img class="lazy loading"  data-original="img/3.jpg">
	</li>
	<li>
		<img class="lazy loading"  data-original="img/4.jpg">
	</li>
</ul>

  src放置loading效果的图片，data-original放置实际的图片路径，设置class为lazy（必须）
```
```
<script type="text/javascript">
   $(function() {
      $("img.lazy").lazyload({
          placeholder : "img/logo.png",     //用图片提前占位
          effect : "fadeIn",  //载入使用何种效果,effect(特效),值有show(直接显示),fadeIn(淡入),slideDown(下拉)等
          failurelimit : 10,  //图片排序混乱时 ,
          threshold : 200,    //提前开始加载
          event : "click",   //事件触发时才加载,event,值有click(点击),mouseover(鼠标划过),sporty(运动的),foobar(…).
          load:function(elements_left, settings) {  
                  $(this).removeClass("loading");  
              }  //在对应图片延时加载完成后removeClass
        });
    });
</script>
```

## 参数
```
placeholder : "img/grey.gif",     //用图片提前占位
effect : "fadeIn",    //载入使用何种效果,effect(特效),值有show(直接显示),fadeIn(淡入),slideDown(下拉)等,常用fadeIn
threshold : 200,    //提前开始加载
event : "click",      //事件触发时才加载,event,值有click(点击),mouseover(鼠标划过),sporty(运动的),foobar(…).
                        可以实现鼠标划过或点击图片才开始加载,后两个值未测试…
failurelimit : 10,     //图片排序混乱时 ,
failurelimit,值为数字.
```

# 转盘抽奖(大转盘（指针转）)turntable2
效果如下：
![](images/img.gif)

html code:
```
<!doctype html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=640"/>
	<title>转盘抽奖(大转盘（指针转）)</title>
	<style>
		body{background:url(images/bg.png) 0 0 repeat;}
		.rotate-con-pan{
			background:url(images/disk.jpg) no-repeat 0 0;background-size:100% 100%;
			position:relative;
			width:480px;
			height:480px;
			box-sizing:border-box;
			-moz-box-sizing:border-box;
			-webkit-box-sizing:border-box;
			margin:0 auto
		}
		.rotate-con-zhen{
			width:112px;
			height:224px;
			background:url(images/start.png) no-repeat 0 0;
			background-size:100% 100%;
			cursor:pointer;
			position:absolute;
			left:180px;
			top:140px;
		}
	</style>
</head>
<body>
<div class="rotate-con-pan">
	<div class="rotate-con-zhen"></div>
</div>
</body>
</html>
<script src="js/jquery-1.8.0.min.js"></script>
<script src="js/jQueryRotate.2.2.js"></script>
<script src="js/script.js"></script>
<script>
	$(function(){
		$(".rotate-con-zhen").rotate({
			bind:{
				click:function(){
					var a = runzp();
					$(this).rotate({
						duration:3000,               //转动时间
						angle: 0,                    //起始角度
						animateTo:1440+a.angle,      //结束的角度
						easing: $.easing.easeOutSine,//动画效果，需加载jquery.easing.min.js
						callback: function(){
							alert(a.prize+a.message);//简单的弹出获奖信息
						}
					});
				}
			}
		});
	});
</script>
```


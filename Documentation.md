# Introduction #

jqSlider is a jQuery horizontal image slider which uses a preview bar of image pieces upon hover and a transition between actual and new image.


# HTML Structure and Integration #

It's very important that slide-wrapper class has a fixed size. Otherwise the plugin won't work.

```
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
<html>
<head>
	<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
	<title>jqSlider</title>
	<script type="text/javascript" src="jquery-1.4.2.min.js"></script>
	<script type="text/javascript" src="jquery.jqslider-0.3.min.js"></script>
	<style type="text/css">
		
		* {
			font-family:"Trebuchet MS",Verdana,Arial,sans-serif;
			font-size:12px;
			color:#000;
			margin:0;
			padding:0;
		}
		body {
			margin:10px;
			background-color:#fff5dd;
		}

		.slide-wrapper {
			width:800px;
			height:520px;
			overflow:hidden;
			position:relative;
			margin-bottom:10px;
		}
		
		.slide-view {
			width:100%;
			height:100%;
			overflow:hidden;
			position:relative;
		}
		.slide-view-back,
		.slide-view-front {
			position:absolute;
			top:0;
			left:0;
			height:100%;
			overflow:hidden;
		}
		.slide-title {
			position:absolute;
			left:0;
			bottom:0;
			padding:5px;
			text-shadow:1px 1px 0 #000;
			color:#fff;
			height: 1em;
			filter: Shadow(Color=#000000, Direction=135, Strength=1);
		}
		
		.slide-controls {
			position:absolute;
			top:0;
			height:100%;
			overflow:hidden;
		}
		.slide-previews {
			list-style:none;
			display:inline;
			margin:0;
			padding:0;
			background-color:#ff0000;
		}
		.slide-previews:after {
			content:".";
			visibility:hidden;
			height:0;
			display:block;
			clear:both;
		}
		.slide-previews li {
			height:100%;
			overflow:hidden;
			float:left;
			display:inline-block;
		}
		
	</style>
</head>
<body>
	<div id="slide-1" class="slide-wrapper">
		<div class="slide-view">
			<div class="slide-view-back">
				<img src="slide1.jpg" /><div class="slide-title">New York</div>
			</div>
			<div class="slide-view-front">
				<img src="slide1.jpg" /><div class="slide-title">New York</div>
			</div>
		</div>
		<div class="slide-controls">
			<ul class="slide-previews">
				<li><img src="slide1.jpg" title="New York" /></li>
				<li><img src="slide2.jpg" title="Paris" /></li>
				<li><img src="slide3.jpg" title="Beachgirl" /></li>
				<li><img src="slide4.jpg" title="Tennis Player" /></li>
				<li><img src="slide5.jpg" title="Sports Car" /></li>
			</ul>
		</div>
	</div>
	<div id="slide-2" class="slide-wrapper">
		<div class="slide-view">
			<div class="slide-view-back">
				<img src="slide1.jpg" /><div class="slide-title">New York</div>
			</div>
			<div class="slide-view-front">
				<img src="slide1.jpg" /><div class="slide-title">New York</div>
			</div>
		</div>
		<div class="slide-controls">
			<ul class="slide-previews">
				<li><img src="slide1.jpg" title="New York" /></li>
				<li><img src="slide2.jpg" title="Paris" /></li>
				<li><img src="slide3.jpg" title="Beachgirl" /></li>
				<li><img src="slide4.jpg" title="Tennis Player" /></li>
				<li><img src="slide5.jpg" title="Sports Car" /></li>
			</ul>
		</div>
	</div>
	<script type="text/javascript">
	/* <![CDATA[ */
		$(document).ready(function() {
			$(".slide-wrapper").each(function() {
				$(this).jqSlider();
			});
		});
	/* ]]> */
	</script>
</body>
</html>
```


# Configuration #

There are severel configuration options for jqSlider. It's possible to define the size of preview bar for each image, if there should be animated transitions for images and/or controls and how fast they perform.

```
<script type="text/javascript">
/* <![CDATA[ */
	$(document).ready(function() {
		$(".slide-wrapper").each(function() {
			$(this).jqSlider({
				debug: true,			// enable debugging
				barSize: 25,			// size of preview bar per image
				speedTransition: 300,		// speed of image transition
				speedOpacity: 300,		// speed of controls transition
				transitionAnimated: true,	// animate image transition
				opacityAnimated: true,		// animate controls transition
			});
		});
	});
/* ]]> */
</script>
```
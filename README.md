# Let's aggregate some .js files

Tired of all these `<script>`? 

**js_monticule.php** is a little php script that aggregate all your .js 
files in one, with full automatic versioning and async optimization.

1. Drag **js_monticule.php** on your web server

2. Include and call **js_monticule.php** within your page *via*: 

		<?php
		include_once("js_monticule.php");
		js_monticule("file1.js","file2.js","file3.js");
		?>
it will automatically generate this asynchronous snippet: 

		<script type="text/javascript">
		(function(){
			var monticule = document.createElement('script');
			monticule.type = 'text/javascript';
			monticule.async = true;
			monticule.src = 'js_monticule_cache/0850000225d05d25cb4f1b6ee428f6dd_2668932196_94890_monticule.js';
			(document.getElementsByTagName('head')[0]||document.getElementsByTagName('body')[0]).appendChild(monticule);
		})();
		</script>
you need a classic synchronous script tag? use: 

		<?php
		include_once("js_monticule.php");
		js_monticule("file1.js","file2.js","file3.js",false);
		?>
to generate: 

		<script type="text/javascript" src="js_monticule_cache/0850000225d05d25cb4f1b6ee428f6dd_2668932196_94890_monticule.js"></script>
		
3. That's all. **js_monticule.php** take care of the rest.
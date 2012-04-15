# Let's merge some .js files

Tired of all these `<script>`? 

**js_monticule.php** is a little php script that aggregate all your .js 
files in one, with full automatic versioning and async optimization.

## Setup

1. Drag **js_monticule.php** on your web server

2. Include and call **js_monticule.php** within your page *via*: 

		<?php
		include_once("js_monticule.php");
		js_monticule("file1.js","file2.js","file3.js");
		?>
it will automatically generate this asynchronous snippet: 

		<script type="text/javascript">
		(function(){
			var m = document.createElement('script');
			m.type = 'text/javascript';
			m.async = true;
			m.src = 'js_monticule_cache/0850000225d05d25cb4f1b6ee428f6dd_2668932196_94890_monticule.js';
			(document.getElementsByTagName('head')[0]||document.getElementsByTagName('body')[0]).appendChild(m);
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

## MIT Licence

**js_monticule.php**

Copyright (c) 2012 Nikki Moreaux, http://diplodoc.us

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
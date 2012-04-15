# Let's aggregate some .js files

Tired of all these <script>?

1. Drag **js_monticule.php** on your web server

2. Include and call **js_monticule.php** with ‘<head>
	<meta charset="UTF-8">
	<title>js_monticule.php demo</title>
	
	<?php
	
	include_once("js_monticule.php");
	js_monticule("./javascript/jquery.js","./javascript/backbone.js","./javascript/index.js");
	
	?>
	
</head>’
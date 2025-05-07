### Web Technologies

HTML - basic tech that a webpage is built on - Can be checked for potential XXS

```
<!DOCTYPE html>
<html lang="en">
<meta charset="UTF-8">
<title>Web page title</title>
<link rel="stylesheet" href="css/styles.css">
<style>
</style>
<script src="js/animation.js"></script>
<body>

	<img src="logo.jpg" alt="logo" style="width:30%">

	<div class="container">
		<h1>This is a Heading</h1>
		<p>This is a paragraph</p>
		<p>This is another paragraph</p>
	</div>

</body>
</html>
```

CSS - Cascading style sheets - defines the look and feel of a website.  Colors, styles, menus, etc.  Not all that helpful for bug bounty or pentesting.

```
<link rel="stylesheet" href="css/styles.css">
```

Scripts - Mainly javascript (.js), these add functionality to a website and make them interactive.  Also nodejs is gaining popularity.

```
<script src="js/animation.js"></script>
```

Client-side - The browser and the user's end

Server-side - Is the backend of a website, the db, and other items


Traditional Web Apps - return full page reloads for every request, server plays a larger role in gerating page content

Modern Web Apps - Loading data in the background and uses other means to refresh portions of a page vs the entire page.
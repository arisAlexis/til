putting an SPA's main script include on the bottom of the body tag can save us from weird errors.

In a fast browser, including the main script before the ID elements made RactiveJS not to render because it found no elements.

even then, the SPA is better to start after the document ready event.

example with JSPM:

```HTML
<html lang="en">
<head>
  <script src="https://code.jquery.com/jquery-2.2.0.min.js"></script>
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js" integrity="sha384-0mSbJDEHialfmuBBQP6A4Qrprq5OVfW37PRR3j5ELqxss1yVqOtnepnHVP9aJ7xS" crossorigin="anonymous"></script>
</head>
<body>
  <script src="jspm_packages/system.js"></script>
  <script src="config.js"></script>
  <script>System.import('./js/main')</script>
</body>
```

if the main script runs `$('#someId').tooltip();` it will fail. So the whole application should start in a document ready in main.js like this:

```javascript
$(document).ready(function() {
  router.start();
});
```



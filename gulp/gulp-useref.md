### Parse build blocks in HTML files to replace references to non-optimized scripts or stylesheets.

<https://www.npmjs.com/package/gulp-useref>

It can handle file concatenation but not minification. Files are then passed down the stream. For minification of assets or other modifications, use gulp-if to conditionally handle specific types of assets.

Usage The following example will parse the build blocks in the HTML, replace them and pass those files through. Assets inside the build blocks will be concatenated and passed through in a stream as well.

```html
<!-- build:<type>(alternate search path) <path> <parameters> -->
... HTML Markup, list of script / link tags.
<!-- endbuild -->

```


>
● type: either js, css or remove; remove will remove the build block entirely without generating a file

> ● alternate search path: (optional) By default the input files are relative to the treated file. Alternate search path allows one to change that

> ● path: the file path of the optimized file, the target output

> ● parameters: extra parameters that should be added to the tag

An example of this in completed form can be seen below:

```html

<!-- build:css css/combined.css -->
<link href="css/one.css" rel="stylesheet">
<link href="css/two.css" rel="stylesheet">
<!-- endbuild -->


<!-- build:js scripts/combined.js -->
<script type="text/javascript" src="scripts/one.js">
</script>
<script type="text/javascript" src="scripts/two.js">
</script>
<!-- endbuild -->

```

### The resulting HTML would be:

```html

<link rel="stylesheet" href="css/combined.css">
<script src="scripts/combined.js">
</script>

```

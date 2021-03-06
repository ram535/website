+++
title = "Part02 entry point"
+++

**index.html** is the entry point of the whole program.
We are going to add a textarea tag with these propierties id="editor", 80 columns width and autofocus.

{{< highlight html "linenos=inline,hl_lines=15" >}}
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>part02</title>
    <link rel="stylesheet" href="styles.css">
    <link rel="icon" href="favicon.ico">
    <script defer src="main.dart" type="application/dart"></script>
    <script defer src="packages/browser/dart.js"></script>
</head>

<body>
  <div id="output"></div>
  <textarea  id="editor"  cols="80"  autofocus></textarea>
</body>
</html>
{{< /highlight >}}

That's it. From here on the next parts of the tutorial we are just going to add functionalities based on what the user type on
the **`<textarea></textarea>`** tag.

Run **pub serve** on the root of the project and go to **`http://localhost:8080/`** in your browser.

Result: [part02](https://ram535.github.io/text-editor-dart/part02/index.html).

Check the [source code](https://github.com/ram535/text-editor-dart/tree/master/part02).

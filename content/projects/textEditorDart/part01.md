+++
title = "Part01 entry point of the webapp"
date = 2017-09-23T16:27:46+02:00
+++

We are going to start really simple. The first thing we have to do is to create a html file.
This file is the entry point of the whole program.

We are goint to called it index.html.

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Text Editor Dart</title>
    </head>

    <body>
            <textarea  id="editor"  cols="80"  autofocus></textarea>
    </body>
</html>
```

That's it. We just add a textarea tag with these propierties id="editor", 80 columns width and autofocus.

This is the result of [part01](https://ram535.github.io/text-editor-dart/part01/index.html).

Check the [source code](https://github.com/ram535/text-editor-dart/tree/master/part01).

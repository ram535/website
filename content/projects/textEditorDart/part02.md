+++
title = "Part02 modifying index.html"
date = 2017-09-24T16:27:46+02:00
+++

`index.html` is the entry point of the whole program.
We are going to add a textarea tag with these propierties id="editor", 80 columns width and autofocus.

``` html
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

That's it. From here on the next parts of the tutorial we are just going to add functionalities based on what the user type on
the `<textarea></textarea>` tag.

This is the result of [part02](https://ram535.github.io/text-editor-dart/part02/index.html).

Check the [source code](https://github.com/ram535/text-editor-dart/tree/master/part02).

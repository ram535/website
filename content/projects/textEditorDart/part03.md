+++
title = "Part03 selecting and modifying a tag by id"
+++

Let's create a variable that will connect to .

{{< highlight dart "linenos=inline,hl_lines=5 6" >}}
import 'dart:html';

void main() {
  querySelector('#output').text = 'Your Dart app is running.';
  TextAreaElement theEditor = querySelector("#editor");
  theEditor.value = "welcome to the dart text editor";
}
{{< /highlight >}}

The **dart:html** package is part of the dart SDK and contains methods and properties that cover the DOM.
That is why we are able to declare the variable **theEditor** of type **TextAreaElement** and use the method
**querySelector** to connect it to the **`<textarea id="editor" cols="80" autofocus></textarea>`** element by id.

Now that we connect the **`<textarea></textarea>`** element to the **theEditor** variable
is possible to modify it throw the variable. In this case we choose to add a value to the tag.

Run **pub serve** on the root of the project and go to **`http://localhost:8080/`** in your browser.

Result: [part03](https://ram535.github.io/text-editor-dart/part03/index.html).

Check the [source code](https://github.com/ram535/text-editor-dart/tree/master/part03).

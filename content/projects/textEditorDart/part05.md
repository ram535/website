+++
title = "Part05 Adding a clear button"
+++

Let's add the button tag in the **index.html** with an id of **btnClearText**.

{{< highlight html "hl_lines=15" >}}
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>part05</title>
        <link rel="stylesheet" href="styles.css">
        <link rel="icon" href="favicon.ico">
        <script defer src="main.dart" type="application/dart"></script>
        <script defer src="packages/browser/dart.js"></script>
    </head>

    <body>
        <textarea id="editor" cols="80" autofocus></textarea>
        <button id="btnClearText">Clear</button>
    </body>
</html>
{{< /highlight >}}

Now let's connect this button **clearEditor()** function in the **main.dart** file.
Everytime the clear button is click the **clearEditor()** function is call, then we assign an empty
string to **theEditor.value** and finally we reuse the **saveDocument()** function to save to the **Local Storage**.

{{< highlight dart "hl_lines=11-12 28-31">}}
import 'dart:html';
import 'dart:convert' show JSON;

TextAreaElement theEditor = querySelector("#editor");

void main() {
  theEditor
    ..value = loadDocument()
    ..onKeyUp.listen((_) => saveDocument());

  ButtonElement btnClear = querySelector("#btnClearText");
  btnClear.onClick.listen((_) => clearEditor());
}

String loadDocument() {
  String jsonString = window.localStorage["TextEditor"];
  print(jsonString);
  if (jsonString != null && jsonString.length > 0)
    return JSON.decode(jsonString);
  else
    return "";
}

void saveDocument() {
  window.localStorage["TextEditor"] = JSON.encode(theEditor.value);
}

void clearEditor() {
  theEditor.value = "";
  saveDocument();
}

{{< /highlight >}}

Run **pub serve** on the root of the project and go to **`http://localhost:8080/`** in your browser.

Result: [part05](https://ram535.github.io/text-editor-dart/part05/index.html).

Check the [source code](https://github.com/ram535/text-editor-dart/tree/master/part05).

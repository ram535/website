+++
title = "Part04 saving the text in the Local Storage"
+++

First let's delete everything that we don't need for our text editor in our **main.dart** file.

{{< highlight dart >}}
import 'dart:html';

void main() {
  TextAreaElement theEditor = querySelector("#editor");
}
{{< /highlight >}}

We are going to use **Local Storage** which is a build-in functionality of HTML5.

{{< highlight dart "linenos=inline,hl_lines=2 6-8 11-17 19-21" >}}
import 'dart:html';
import 'dart:convert' show JSON;

void main() {
  TextAreaElement theEditor = querySelector("#editor");
  theEditor
    ..value = loadDocument()
    ..onKeyUp.listen((_) => saveDocument(theEditor));
}

String loadDocument() {
  String jsonString = window.localStorage["TextEditor"];
  if (jsonString != null && jsonString.length > 0)
    return JSON.decode(jsonString);
  else
    return "";
}

void saveDocument(TextAreaElement theEditor) {
  window.localStorage["TextEditor"] = JSON.encode(theEditor.value);
}
{{< /highlight >}}

First we import the **dart:convert** library which we will use to transform the **theEditor.value** to json format (encode)
since **LocalStorage** requires that its items to be json format and untransform it to a simple string (decode)for **theEditor.value**.
With the keyword **show**, we just make it more clear that we are only want to use this property from the library and it makes more clear our intentions.

``` dart
import 'dart:convert' show JSON;
```

After that we use cascate notation in the theEditor object which make more easy to read the code. <br>
We call the **loadDocument()** function and assign its return value (a string) to the **theEditor.value**.<br>
Then we call the **onKeyup.listen** method which will be listen to every key stroke we made until we finish the application (in this case closing the browser).<br>
On every stroke **onKeyup.listen** will call an anonymous function **(_)** and this anonymous functon will call the **saveDocument()** function.<br>
The **onKeyup.listen()** method returns a object of type **KeyboardEvent** but since we won't be using it, we descart it with the **_** in the anonymous function.

``` dart
  theEditor
    ..value = loadDocument()
    ..onKeyUp.listen((_) => saveDocument(theEditor));
```

In the **loadDocument()** first we assign the content of "Local Storage" by passing a key value in this case **TextEditor** using the **window.localStorage[]** method.
If **window.localStorage[]** does not find the key (TextEditor) it will asing **null** to **jsonString** variable.
Then we check if **jsonString** is not equal to null and bigger its length is bigger than zero just to double check if there is a value in the **Local Storage**.
If there is a value we use the **JSON.decode()** to transform the value from json format to just a simple string.
And if there is not a value in the "Local Storage" we return and empty string.

``` dart
String loadDocument() {
  String jsonString = window.localStorage["TextEditor"];
  print(jsonString);
  if (jsonString != null && jsonString.length > 0)
    return JSON.decode(jsonString);
  else
    return "";
}
```

In the saveDocument() function we recieve the **theEditor** variable an assign its value to the **Local Storage** with the key **TextEditor**
but first we transform it to json format using the **JSON.encode()** method.

``` dart
void saveDocument(TextAreaElement theEditor) {
  window.localStorage["TextEditor"] = JSON.encode(theEditor.value);
}

```

Run **pub serve** on the root of the project and go to **`http://localhost:8080/`** in your browser.

Result: [part04](https://ram535.github.io/text-editor-dart/part04/index.html).

Check the [source code](https://github.com/ram535/text-editor-dart/tree/master/part04).

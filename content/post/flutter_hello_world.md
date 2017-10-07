+++
title = "Flutter Hello World"
date = 2017-10-05T14:46:50+02:00
Description = ""
Tags = []
Categories = ["flutter"]
+++

To install flutter follow this steps:

- clone the [repo](git clone -b alpha https://github.com/flutter/flutter.git)
- add the path on your machine (adjust the path that correspond to your machine)

```
export PATH=$HOME/projects/flutter/bin:$PATH
```

- run **flutter doctor** to see if there are any dependencies you need to install to complete the setup

Now let's create a flutter project

```
flutter create flutter_hello_world
```

We can use a simulator or a divice to test the demo app.
For me is more easy to do it in actual device because is faster than using a simulator.
Connect the device to your computer and go **Settings>About** phone and tapping the Build number line seven times enable USB debugging.
Let's check if our devices is detected by running this command:

```
flutter devices
```

Let's run the demo app to check that everything set up right.

```
cd myapp
flutter run
```

![image](../../img/flutter-hello-world-demo.jpg)

Go to **lib/main.dart** and modify the main funtion.

{{< highlight dart >}}
import 'package:flutter/material.dart';
void main() {
  runApp(const Center(
      child: const Text(
    'Hello, world!',
    textDirection: TextDirection.ltr,
  )));
}
{{< /highlight >}}

+++
title = "Setting up an Angular Dart Project"
date = 2017-10-09T11:55:01+02:00
Description = ""
Tags = []
Categories = []
+++

First we are going to install **stagehand** program using the **pub** package manager.

{{< highlight sh >}}
pub global active stagehand
{{< /highlight >}}

**Pub**’s global option allows you to run Dart scripts from the command line when you are not currently inside a package.
Now run **pub global list** to see all the install global package.

{{< highlight sh >}}
stagehand 1.1.6
{{< /highlight >}}

In this case there is only one packages install. **stagehand** generates the scaffolding of the project you choose
for example a simple web app, an angular app, etc.

Let's create the scaffolding for a angular app by running this command.

{{< highlight sh >}}
stagehand web-angular
{{< /highlight >}}

This will generate the next directories and files for an angular dart app.

{{< highlight sh >}}
.
├── analysis_options.yaml
├── CHANGELOG.md
├── lib
│   ├── app_component.css
│   ├── app_component.dart
│   ├── app_component.html
│   └── src
│       └── todo_list
│           ├── todo_list_component.css
│           ├── todo_list_component.dart
│           ├── todo_list_component.html
│           └── todo_list_service.dart
├── LICENSE
├── pubspec.yaml
├── README.md
├── test
│   └── app_test.dart
└── web
    ├── favicon.png
    ├── index.html
    ├── main.dart
    └── styles.css
{{< /highlight >}}

Now run these commands to get all the dependecies and start a server:

{{< highlight sh >}}
pub get
pub serve
{{< /highlight >}}

Go to port **`http://localhost:8080`** and you will see this todo app.

![image](../../img/angular-hello-world.jpg)

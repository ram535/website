+++
title = "Setting up an Angular Dart Project"
date = 2017-10-09T11:55:01+02:00
Description = ""
Tags = []
Categories = []
+++

First we are going to install **stagehand** program using the **pub** package manager.

```
pub global active stagehand
```

**Pub**’s global option allows you to run Dart scripts from the command line when you are not currently inside a package.
Now run **pub global list** to see all the install global package.

```
stagehand 1.1.6
```

In this case there is only one packages install. **stagehand** generates the scaffolding of the project you choose.

{{< highlight dart >}}
$ ~ stagehand
Stagehand will generate the given application type into the current directory.

usage: stagehand <generator-name>
    --[no-]analytics    Opt out of anonymous usage and crash reporting.
-h, --help              Help!
    --version           Display the version for stagehand.
    --author            The author name to use for file headers.
                        (defaults to "<your name>")

Available generators:
  console-full   - A command-line application sample.
  package-simple - A starting point for Dart libraries or applications.
  server-shelf   - A web server built using the shelf package.
  web-angular    - A web app with material design components.
  web-simple     - A web app that uses only core Dart libraries.
  web-stagexl    - A starting point for 2D animation and games.
{{< /highlight >}}

Let's create the scaffolding for a angular app by running this command.

```
stagehand web-angular
```

This will generate the next directories and files for an angular dart app.

```
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
```

Now run these commands to get all the dependecies and start a server:

```
pub get
pub serve
```

Go to port **`http://localhost:8080`** and you will see this todo app.

![image](../../img/angular-hello-world.jpg)

This project contains all the bootstrap sass source files. This project
will be useful to create new themes using sass.

`bootstrap_sass` is a Sass-powered version of
[Bootstrap](https://github.com/twbs/bootstrap), ready to drop right into
your Sass powered applications.

# Usage

1 - Create a new project with next structure:

    [project_root]
      ├─ pubspec.yaml
      ├─ web
      │  ├─ index.html
      │  ├─ _variables.scss
      │  ├─ theme.scss
      │  └─ ... other files and folders ...
      └─ lib
         └─ ... lib files and folders ...

2 - In the `pubspec.yaml` file add the `bootstrap_sass` and
`sass_builder` dependencies as
below:

``` yaml
name: bootstrap_sass_example # change this line to have your library name
description: An absolute bare-bones web app.

environment:
  sdk: '>=2.0.0 <3.0.0'

dependencies:
  bootstrap_sass: ^4.5.0
dev_dependencies:
  build_runner: ^1.0.0
  build_web_compilers: ^2.0.0
  sass_builder: ^2.0.0
```

3 - Then in `_variables.scss` add the variables you want to modify

``` scss
//== Colors

$primary:          #e72b42;
$secondary:        #73A839;
$info:             #033C73;
$warning:          #DD5600;
$danger:           #22afc7;
```

4- In the `theme.scss` add next code:

``` scss
@import "variables";
@import "package:bootstrap_sass/scss/bootstrap";
```

5 - Then in the `index.html` you will add the link to `theme.css` as
below:

``` html
  <link rel="stylesheet" href="theme.css">
```

so you will end up with an `index.html` file like next one:

``` html
<!DOCTYPE html>

<html>
<head>
  <meta charset="utf-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="scaffolded-by" content="https://github.com/google/stagehand">
  <title>bootstrap_sass_sample</title>
  <link rel="stylesheet" href="theme.css">
  <link rel="icon" href="favicon.ico">
  <script defer src="main.dart.js"></script>
</head>

<body>

<button class="btn btn-primary">Bootstrap Primary Button</button>
<button class="btn btn-secondary">Bootstrap Secondary Button</button>
<button class="btn btn-success">Bootstrap Success Button</button>
<button class="btn btn-info">Bootstrap Info Button</button>
<button class="btn btn-danger">Bootstrap Danger Button</button>
<button class="btn btn-warning">Bootstrap Warning Button</button>

</body>
</html>
```

6 - Finally to run this project you will need to use next command:

    webdev serve

# Credits

`bootstrap_sass` has a number of major contributors:

  - [Thomas McDonald](https://twitter.com/thomasmcdonald_)

  - [Tristan Harward](http://www.trisweb.com)

  - Peter Gumeson

  - [Gleb Mazovetskiy](https://github.com/glebm)

and a [significant number of other
contributors](https://github.com/dart-league/bootstrap_sass/graphs/contributors).

The Dart port is made by: [Luis Vargas](https://github.com/luisvt)

# Bugs and feature requests

Have a bug or feature request to bootstrap core? Please open a new issue
at <https://github.com/twbs/bootstrap/issues/new>.

Have a bug or feature request to `bootstrap_sass` Dart port? Please open
a new issue at
<https://github.com/dart-league/bootstrap_sass/issues/new>.

# Copyright and license

Code and documentation copyright 2011-2019 the [Bootstrap
Authors](https://github.com/twbs/bootstrap/graphs/contributors) and
[Twitter, Inc.](https://twitter.com) Code released under the [MIT
License](https://github.com/twbs/bootstrap/blob/master/LICENSE). Docs
released under [Creative
Commons](https://github.com/twbs/bootstrap/blob/master/docs/LICENSE).

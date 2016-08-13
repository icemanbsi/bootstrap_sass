# bootstrap_sass

This project contains all the bootstrap sass source files. This project will be useful to create new themes using sass.

`bootstrap_sass` is a Sass-powered version of [Bootstrap](https://github.com/twbs/bootstrap), ready to drop right into your Sass powered applications.

# Usage
1\. [Install sass](http://sass-lang.com/install). If you already installed skip to step number 2\.

2\. Create a new project with next structure:

```
[project_root]
  ├─ pubspec.yaml
  ├─ web
  │  ├─ index.html
  │  ├─ variables.scss
  │  ├─ theme.scss
  │  └─ ... other files and folders ...
  └─ lib
     └─ ... lib files and folders ...
```

3\. In the `pubspect.yaml` file add the `bootstrap_sass` dependency and `sass` dependency, then you will need to add `sass` transformer (this is in charge of converting sass files into css).

```yaml
...
depencencies:
  ...
  bootstrap_sass: any
  sass: any
  ...
transformers:
  ...
  - sass
  ...
```

4\. Then in `variables.scss` add the variables you want to modify

```scss
//== Colors
//
//## Gray and brand colors for use across Bootstrap.

$gray-base: #800625;
$gray-darker:            lighten($gray-base, 13.5%); // #222
$gray-dark:              lighten($gray-base, 20%);   // #333
$gray:                   lighten($gray-base, 33.5%); // #555
$gray-light:             lighten($gray-base, 60%);   // #999
$gray-lighter:           lighten($gray-base, 93.5%); // #eee

$brand-primary:          #e72b42;
$brand-success:          #73A839;
$brand-info:             #033C73;
$brand-warning:          #DD5600;
$brand-danger:           #22afc7;
...
```

5\. In the `theme.scss` add the styles you need to change.

```scss
@import 'variables' // variables should be before bootstrap to override variable values
@import 'packages/bootstrap_sass/stylesheets/bootstrap';

// Cerulean 3.3.5
// Bootswatch
// -----------------------------------------------------

@mixin btn-shadow($color){
  @include gradient-vertical-three-colors(lighten($color, 8%), $color, 60%, darken($color, 4%));
  filter: none;
  border-bottom: 1px solid darken($color, 10%);
}

// Navbar =====================================================================

.navbar {
  @include btn-shadow($navbar-default-bg);
  filter: none;
  @include box-shadow(0 1px 10px rgba(0, 0, 0, 0.1));

  &-default {

    .badge {
      background-color: #fff;
      color: $navbar-default-bg;
    }
  }

  &-inverse {
    @include gradient-vertical-three-colors(lighten($navbar-inverse-bg, 8%), lighten($navbar-inverse-bg, 4%), 60%, darken($navbar-inverse-bg, 2%));
    filter: none;
    border-bottom: 1px solid darken($navbar-inverse-bg, 10%);

    .badge {
      background-color: #fff;
      color: $navbar-inverse-bg;
    }
  }

  .navbar-nav > li > a,
  &-brand {
    text-shadow: 0 1px 0 rgba(0, 0, 0, 0.1);
  }
}
...
```

6\. Finally in the `index.html` you will add the link to `theme.css` as it follows:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <title>Bootstrap Example</title>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <!-- you could add bootstrap.css file -->
  <link rel="stylesheet" href="packages/bootstrap_sass/sass/bootstrap.css">
  <!-- you can also add theme.css -->
  <link rel="stylesheet" href="theme.css">
</head>
<body>
  <!-- ... content here ... -->
</body>
</html>
```

## Credits

bootstrap-sass has a number of major contributors:

<!-- feel free to make these link wherever you wish -->
* [Thomas McDonald](https://twitter.com/thomasmcdonald_)
* [Tristan Harward](http://www.trisweb.com)
* Peter Gumeson
* [Gleb Mazovetskiy](https://github.com/glebm)

and a [significant number of other contributors][contrib].

The dart port is made by: [Luis Vargas](https://github.com/luisvt)

## Bugs and feature requests

Have a bug or a feature request to bootstrap core?  Please open a new issue at https://github.com/twbs/bootstrap/issues/new.

Have a bug or a feature request to bootstrap_sass dart port? Please open a new issue at https://github.com/dart-league/bootstrap_sass/issues/new.

## Copyright and license

Code and documentation copyright 2011-2015 Twitter, Inc. Code released under [the MIT license](https://github.com/twbs/bootstrap/blob/master/LICENSE). Docs released under [Creative Commons](https://github.com/twbs/bootstrap/blob/master/docs/LICENSE).

# Customizing the HPSTR Theme for Octopress
If you're here looking at the source, there's a good chance that you'd like to
go about changing it for your own purposes. With that in mind, here is a quick
overview of how these files are laid out and where are some good places to
start when customizing the theme.

## Requirements
This theme uses a Compass plugin for animations which is aptly called "animation". To install it, follow the instructions [here][compass-animation] to download and install it as a Compass gem for Ruby.

## Layout
This is the basic sass layout:

    sass/
    ├── screen.scss
    │
    ├── _base.scss
    ├── base/
    │   ├── _layout.scss
    │   ├── _mixins.scss
    │   ├── _pygments.scss
    │   ├── _reset.scss
    │   ├── _typography.scss
    │   ├── _utilities.scss
    │   └── _variables.scss
    │
    ├── _partials.scss
    ├── partials/
    │   ├── _animations.scss
    │   ├── _buttons.scss
    │   ├── _dl-menu.scss
    │   ├── _elements.scss
    │   ├── _entryheader.scss
    │   ├── _figures.scss
    │   └── _readmore.scss
    │
    ├── custom/
    │   ├── _colors.scss
    │   ├── _fonts.scss
    │   └── _styles.scss
    │
    └── plugins/
        └── _coderay.scss

The first files to be loaded are `custom/_colors.scss` and
`custom/_styles.scss`, which allow you to alter the default values for the
variables used throughout the sass project. For more information on how this
works, see [here][sass-defaults].

The files `_base.scss` and `_partials.scss` just import the partials from the
corresponding folders.

### `base/`
The `base` directory contains the bare bones of the project. It defines default
values for variables used throughout the project, includes a custom CSS reset,
defines various utility classes and mixins, etc. This folder also contains the
styles which define colors used for pygments syntax highlighting. Most of the
heavy lifting for the site's layout is done in `_layout.scss`.

### `partials/`
This directory is oriented around providing styling for specific components.
The file `_dl-menu.scss` defines the transitions for the floating menu on each
page. With the exception of `_elements.scss`, which is just a file of
miscellaneous stylings, most other files are semantically named.

## Where to Start
For simple tweaks to things like colors, fonts, font sizes, line-height, etc.,
see `custom/_colors.scss` and `custom/_fonts.scss`. If you change values in
these files, they will override the defaults, which can always be viewed in
`base/_variables.scss`.

Note that to load a new web font, you can simply use the CSS3 `@import`
directive to pull down a shiny new font descriptor. If you're worried about
page load times (and you should be) and you remove the 'Lato' font as the
default font, be sure to edit `base/_variables.scss` to remove its import line.

# Internals
There's a lot of good stuff going on under the hood. For one thing, the site
makes use of CSS keyframes and animations. To automate the process of
generating these, a third party Compass library called 'animation' is used.
See [compass-animation][animation] on GitHub for more documentation.

# Questions
Feel free to send me questions on GitHub or on Twitter ([@Z1MM32M4N][twitterr]).
However, this theme is only a port of the [HPSTR Theme for Jekyll][hpstr-jekyll] by
[mmistakes][mmistakes], so you may want to consider looking through his original
less stylesheets and perhaps ask him questions as needed.

[sass-defaults]: http://sass-lang.com/documentation/file.SASS_REFERENCE.html#variable_defaults_
[compass-animation]: https://github.com/ericam/compass-animation
[twitter]: https://twitter.com/Z1MM32M4N
[hpstr-theme]: https://github.com/mmistakes/hpstr-jekyll-theme
[mmistakes]: https://github.com/mmistakes/

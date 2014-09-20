# HPSTR Theme for Octopress
This is a port of the [HPSTR Theme][HPSTR] by [mmistakes][mmistakes] for Octopress. The theme was initially built for Jekyll and Less; this theme is written entirely in Sass and makes use of the Octopress 2.0 blogging framework.

## Preview
To see a live preview of the theme, check out mmistakes's [live Jekyll version][jekyll-preview]. You can also feel free to check out [blog.zimmerman.io][blog] which currently uses the HPSTR theme for Octopress (you can also check out the source of this repo to get a feel for getting the theme to work with an Octopress installation.) 

## Installation
### Requirements
This theme uses a Compass plugin for animations which is aptly called "animation". To install it, follow the instructions [here][compass-animation] to download and install it as a Ruby gem for Compass.

### Walkthrough
> #### Hey you with the trigger happy command line
> Before you run the following commands, if you already have an Octopress theme installed, you may want to move your `source/` and `sass/` folders to `source.bak/` and `sass.bak/`, respectively. During the Octopress installation process, any residual files from old themes that are not overwritten can pollute your source directory and cause confusing build errors. To avoid this, simply back up these files and restore those specific files which are specific to your blog (i.e., special pages you may have introduced and all of your `_posts/` directory, among other files).

Installing themes in Octopress 2.0 is done using the `.themes` directory of your project.
```bash
$ cd your-octopress-blog
$ git clone https://github.com/Z1MM32M4N/hpstr-theme.git .themes/hpstr
$ rake install['hpstr']
$ rake generate
```
> ### Note
> If the `rake` commands don't work, you may have to try `bundle exec rake`, depending on how you have ruby installed on your system.

### Setting up your `_config.yml` and `config.rb`
This theme requires a lot of changes to your `_config.yml`, which are all documented [here](Properties.md). Make sure you check it out and add the new required fields.

For the stylesheets to be loaded properly, you need to configure Compass to generate your static file assets into the `source/` folder. This can be done in `config.rb`. By prefixing all the output paths (`css_dir` in particular) with '`source/`', Compass will know that it should actually place the generated files inside of folders within the `source/` directory. 

You will also need to add one line to your `config.rb` for Sass to compile the animations, if you didn't already. (This is the line "`require 'animation'`" as documented in the requirements for installation above.)

### Caveats
The third party Compass plugin to handle animations doesn't like to play well with the features Octopress provides to automate the build process, `rake generate` and `rake preview`. When running either of these commands, Octopress complains that it can't find the Compass plugin 'animation'. However, with an otherwise successful installation of the plugin, running `compass compile` and `compass watch` will build the Sass without error.

There is a GitHub issue filed [here][compass-issue] if you would like to follow along, offer a solution, or see what others have to say (though I doubt this will get much attention in the light of Octopress 3.0).
## What Next
There are a lot of cool things you can do after installing HPSTR for Octopress.

#### Get blogging!
After installing this theme, especially on a fresh Octopress blog, you should be able to start blogging right away. If you can't, let me know in an issue. I'd love to see if I can help you troubleshoot or to fix bugs in my handiwork.

#### Read the docs!
You can read about the Sass documents [here](sass/README.md), and about the various properties that are used throughout the configuration files and front matter [here](Properties.md). I __really__ care about well documented code, so if there's something you think could be explaned better or you need help navigating something, _please_ submit an issue or send me a message [on Twitter](https://www.twitter.com/Z1MM32M4N).

#### Submit Pull Requests!
I didn't port every feature to Octopress. Instead, I focused mostly on just those which I thought I would personally use. If you like this theme but I left out your favorite feature, be sure to fork this repo, add in your feature _in a separate feature branch_, and submit a pull request. 

## Octopress 3.0
Octopress 3.0 is [in the works][v3]! This release, however, is [going to be vastly different][migration] from Octopress 2.0. In Octopress 3.0, [Octopress Ink][ink] will become the method through which themes are created, distributed, and updated, leaving the old method of creating themes used by version 2.0 behind.

Until version 3.0 becomes generally available, you've got a couple of options. The first is obviously to download Octopress 2.0, install HPSTR, and start blogging. This is certainly a viable option, and I'm more than willing to help you if you run into glitches. 

The second is to start a Jekyll blog, perhaps by forking mmistakes's HPSTR Theme, and start using the Octopress 3.0 release candidates to manage your blog. As [imathis][imathis] has admitted, as of the time of this writing these release candidates are [not a finished product][migration], which may leave users feeling unsatisfied.

The third option is to wait it out. This certainly doesn't solve the immediate problem of wanting to get a blog up and running, but it has some unique advantages. For one, you don't have to dabble with a buggy and bloated 2.0 codebase. Additionally, by waiting for Octopress Ink to come out and waiting for HPSTR to be ported to it, installing new themes and updating them at any time will likely be a cinch.

I'm sure that there are many more options, not the least of which is to go build your own blogging platform, but these three are pretty good all things considered. Pick whichever you feel best meets your wants and needs.

[HPSTR]: https://github.com/mmistakes/hpstr-jekyll-theme
[mmistakes]: https://github.com/mmistakes/
[jekyll-preview]: http://mmistakes.github.io/hpstr-jekyll-theme/
[blog]: http://blog.zimmerman.io/
[v3]: https://github.com/octopress/octopress
[migration]: https://github.com/octopress/octopress/issues/30
[ink]: https://github.com/octopress/ink
[imathis]: https://github.com/imathis
[compass-animation]: https://github.com/ericam/compass-animation
[compass-issue]: https://github.com/imathis/octopress/issues/1570

## License
HPSTR for Octopress
Copyright (C) 2014  Jacob Zimmerman

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.

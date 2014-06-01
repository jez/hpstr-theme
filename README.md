# HPSTR Theme for Octopress

This is a port of the [HPSTR Theme][HPSTR] by [mmistakes][mmistakes] for Octopress. The theme was initially built for Jekyll and Less; this theme is written entirely in Sass and makes use of the Octopress 2.0 blogging framework.

## Installation
Installing themes in Octopress 2.0 is done in the `.themes` directory of your project.
```bash
$ cd your-octopress-blog
$ git clone https://github.com/Z1MM32M4N/hpstr-theme.git .themes/hpstr
$ rake install['hpstr']
$ rake generate
```
If the `rake` commands don't work, you may have to try `bundle exec rake`, depending on how you have ruby installed on your system.

## What Next
There are a lot of cool things you can do after installing HPSTR for Octopress.

#### Get blogging!
After installing this theme, especially on a fresh Octopress blog, you should be able to start blogging right away. If you can't, let me know in an issue. I'd love to see if I can help you troubleshoot or to fix bugs in my handiwork.

#### Read the docs!
You can read about the Sass documents [here](sass/README.md), and about the various properties that are used throughout the configuration files and front matter [here](Properties.md). I __really__ care about well documented code, so if there's something you think could be explaned better or you need help navigating something, _please_ submit an issue or send me a message [on Twitter](https://www.twitter.com/Z1MM32M4N).

#### Submit Pull Requests!
I didn't port every feature to Octopress. Instead, I focused mostly on just those which I thought I would personally use. If you like this theme but I left out your favorite feature, be sure to fork this repo, add in your feature _in a separate feature branch_, and submit a pull request. 

[HPSTR]: https://github.com/mmistakes/hpstr-jekyll-theme
[mmistakes]: https://github.com/mmistakes/

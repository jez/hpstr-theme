# Properties
This document lists all the properties you can and should populate which are not already well documented by Octopress in order to take full advantage of all the Octopress/HPSTR goodness available. 

__All properties prefixed with `site` should be populated in `_config.yml` in the root directory of the project.__ (You should omit the `site` prefix when entering them: this will be automatically added when Jekyll generates the site.)

__All properties prefixed with `page` should be populated per article in the front-matter of each post in the `source/_post` directory.__ (Again, you should omit the `page` prefix when entering these properties: this will be automatically added when jekyll generates the site.)

> ### Note to HPSTR for Jekyll Users:
> If you are migrating from a plain Jekyll/HPSTR blog setup, you will want to pay careful attention to these properties to see which have changed.
> 
> In most cases, the decision was made to make property names in the Octopress spirit. While I agree that the HPSTR for Jekyll organization is _much_ better, my main intention was to make the experience as seamless as possible for existing Octopress users.

## Global Properties (`site.*`)
### New HPSTR Properties
The following properties exist in the HPSTR for Jekyll theme, and must be added to your `_config.yml` file if you want to take advantage of it's functionality.  Most have to do with customizing the drop down menu.
<!-- TODO make the /images/ dir (and all static dirs) configurable -->
- `site.keywords`
    - Allows you to specify site-level keywords to be added to the header of every page.
- `site.avatar`
    - The path of an avatar image, relative to the `/` for your site, to be displayed in the drop down menu . Example:
      `avatar: /images/my-picture.jpg`
    - Note that this could also be the address of an external link by instead including `http://` and then the link.
- `site.author_bio`
    - A short description to be displayed in the 'About' link of the drop down menu.
- `site.links`
    - This property can take a list of links to display on the top level of the drop down menu. Examples:
          
          # In _config.yml:
          links:
            - title: Extra Link in Menu
              url: /my-cool-internal-link
            - title: External Link
              url: http://www.example.com/
              external: true
- `site.background`
    - The default background image to use for the site. See `page.image.background` for more information on how this is used.
- `site.keywords`
    - A set of keywords to append to the keywords meta tag on every page. The other tags will come from the `page.categories` list, as described below.
- `site.logo`
    - Contains the URL of an image which represents the "logo" for your site.  This will not be displayed anywhere on your site except that it will be used by other services (like Facebook) when displaying a feature link to your site.

### Octopress Standard Properties
If this is not your first time using Octopress, you will likely already have these properties populated (if you want them).

#### Author & Miscellaneous
- `site.url`
    - Describes the location of your published blog. (__Note__: this is not used for any internal links in HPSTR for Octopress. Instead, the `site.root` property is used to form links relative to the root of your deployed domain name. See below for more info.)
    - Throughout the HPSTR theme, you may see the variable `root_url` used widely. This is a calculated variable which is based on `site.root` (below), but with the final slash stripped off.
- `site.title`
    - Your blog's title. Will be displayed on the landing (index) page of your generated blog.
- `site.subtitle`
    - A subtitle for your blog. Will be displayed on the landing (index) page of your generated blog under the title.
- `site.author`
    - The author of your blog. __HPSTR for Jekyll migration note__: this property does not already exist for you. Instead, it exists under the name `site.owner.name`.
- `site.simple_search`
<!-- TODO Implement simple site search -->
    - Does not actually do anything yet. Not a Jekyll property.
- `site.description`
    - A short description of the blog to be used as metadata in page headers.
- `site.email`
    - The main email address of the author. __HPSTR for Jekyll migration note__: this property does not already exist for you. Instead, it exists under the name `site.owner.email`.
- `site.learn_more_link`
    - Customization of the `Learn more` link in the dropdown menu.

#### Jekyll & Plugins
- `site.root`
    - This is the property which is used as the base for generating all interior links. When it is actually used, the trailing slash is removed.  For example, if you want to have the index of your blog served at www.example.com/, then you'll want to enter `root: /`. If you want it at `www.example.com/foo/bar/baz/`, then enter `/foo/bar/baz/`. (Note the leading slash. If this is absent, the browswer will attempt to make all links external, and likely fail.)
- `site.recent_posts`
    - Recent posts are displayed at the bottom of each article as "Read More" links. Three articles are displayed: one main article and two smaller.  Thus, this variable is not configurable as it would be in Octopress.
- `site.asides`
    - There are no asides in this theme (as there is no sidebar). Setting this variable will do nothing. The same applies to all other variables which deal with custom asides.

#### 3rd Party Settings
- `site.github_user`
    - The GitHub username for the author. A link will be provided in the drop down menu in the upper left hand corner.
- `site.github_repo_count`, `site.github_show_profile_link`, `site.github_skip_forks`
    - These properties are not used.
- `site.twitter_user`
    - Twitter username without '@' symbol. __HPSTR for Jekyll migration note__: this property does not already exist for you. Instead, it exists under the name `site.owner.twitter`.
- `site.twitter_tweet_button`
    - This property has no function in the HPSTR for Octopress theme. Twitter sharing is enabled on all posts.
- `site.google_plus_one`
    - This property has no function in the HPSTR for Octopress theme. Google+ sharing is enabled on all posts.
- `site.google_plus_one_size`
    - This property has no function in the HPSTR for Octopress theme. A link to your Google+ profile can be provided if `site.googleplus_user` is set.
- `site.googleplus_user`
    - Should represent the entire portion of the url which is unique for your Google+ account, including the '+'. Example: `googleplus_user: +JacobZimmerman0`
- `site.googleplus_hidden`
    - No longer used. If you do not want your Google+ profile to be displayed as a link in the dropdown menu, unset the above variable. Note doing so will remove the author information from search results.
- `site.facebook_like`
    - This property has no function in the HPSTR for Octopress theme. Facebook sharing is enabled on all posts.
- All Pinboard and Delicious customizations have been removed. 
    - Feel free to add them back in by editing the file `_includes/navigation.html` and adding in `<li>` tags for each profile link you wish to display. You may instead just use the `site.links` to add arbitrary custom links. (See above)

## Per Page Properties (`page.*`)
The following properties can be specified in the front-matter for each post.  You may also want to consider front-matter [defaults][defaults] if you are not already using them.
### Octopress

#### Required
- `page.layout`
    - The layout to use for the page.
- `page.title`
    - The title to use for the page.
- `page.description`
    - A short description to use in the meta tags for the site and also for
      the Read More content.

#### Optional
- `page.author`
    - If the author for this particular article is different from the site-level author.
- `page.categories`
    - The categories to file this particular post under. Also prepended to the site-level keywords for use in the SEO of your page.
- `page.comments`
    - Whether to turn comments on or off (must be true for comments to be on).
- `page.external_url`
    - For when the main purpose of your article is to link to a different url.

### HPSTR
- `page.no_header`
    - Remove the author and date information from the top of a post, as well as the link to the comment thread.
- `page.image.feature`
    - The url of an image to be "featured" at the top of the page. Also used when search engine optimizing your site. __This and all other images described in this section should be given as absoloute links.__ (For clarification, see the examples given for the avatar images.)
- `page.image.thumb`
    - If the previous option is not set but you would still like to include a small image thumbnail when SEO'ing your site, you can set this variable with such a link.
- `page.image.credit`
    - If the feature image is set, setting this variable will display a gray box in the bottom right corner of the image with the content credit: {{ page.image.credit }}.
- `page.image.creditlink`
    - Clicking on the gray box mentioned above will take you to the link specified by this variable.
- `page.image.background`
    - The url of a background image for the page. This image will replace the default light gray color of the background on the page.
- `page.share`
    - Boolean. Whether or not to add social sharing links to the page.

[defaults]: http://jekyllrb.com/docs/configuration/#frontmatter-defaults

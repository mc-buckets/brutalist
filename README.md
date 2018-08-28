![version 1](https://img.shields.io/badge/version-1.0-blue.svg?longCache=true)

![Brutalist Pelican Theme](https://brutalistpelican.com/images/site-cover.jpg "Brutalist Pelican Theme") 

View the demo version at [https://brutalistpelican.com](https://brutalistpelican.com).

## Background and Inspiration 
When I decided to get back into blogging, I knew that I wanted a site that was super simple and readable. There are many great Pelican themes out there but I couldn't quite find what I was looking for. After reading David Bryant Copeland's [Brutalist Web Design](https://brutalist-web.design/) a few weeks ago, I was inspired to try and apply those design principles to a Pelican theme. The goal of this theme is to be feature-rich while also accessible and fast. This release is just 1.0. I'll be adding more features as I shake off the front-end coding rust. 

## Features
* Clean, readable, accessible, and fast theme
* Mobile first
* W3C validated
* Clean slugified URLs
* Easy to extend and customize to your liking
* SEO optimized w/ OG tags and Twitter Card support
* Google Analytics support
* Gravatar support
* Disqus support
* Pygments syntax highlighting for code blocks
* Display Twitter, Github, Facebook, Instagram, Strava, Untappd, Telegram, Foursquare, and Goodreads icons in footer if configured

## Template support
### Supported
* archives.html
* period_archives.html
* article.html
* categories.html
* category.html
* index.html
* page.html
* tag.html
* tags.html

### Not supported
* author.html
* authors.html


## Configuration
Here is a list of theme settings you can configure to alter aspects of the theme. The theme also supports most of the general settings that Pelican offers so I won't go into those here.

```python
# Theme Settings
THEME = 'themes/brutalist'
## used for OG tags and Twitter Card data on index page
SITEIMAGE = 'site-cover.jpg'
## used for OG tags and Twitter Card data of index page
SITEDESCRIPTION = 'A simple, accessible, content-first Pelican theme inspired by David Bryant Copeland\'s https://brutalist-web.design/'
## path to favicon
FAVICON = 'pelly.png'
## path to logo for nav menu (optional)
LOGO = 'pelly.png'
## first name for nav menu if logo isn't provided
FIRST_NAME = 'Brutalist'
## google analytics (fake code commented out)
# GOOGLE_ANALYTICS = 'UA-0011001-1'
## Twitter username for Twitter Card data
TWITTER_USERNAME = '@mcman_s'
## Toggle display of theme attribution in the footer (scroll down and see)
## Attribution is appreciated but totally fine to turn off!
ATTRIBUTION = True
## Add a link to the tags page to the menu
## Other links can be added following the same tuple pattern 
MENUITEMS = [('tags', '/tags')]
## Social icons for footer
## Set these to whatever your unique public URL is for that platform
## I've left mine here as a example
STRAVA = 'https://www.strava.com/athletes/27234301'
TWITTER = 'https://twitter.com/mcman_s'
INSTAGRAM = 'https://instagram.com/mcman_s'
GITHUB = 'https://github.com/mamcmanus'
TELEGRAM = 'https://t.me/mcman_s'
GOODREADS = 'https://www.goodreads.com/user/show/48849158-matthew-mcmanus'
FOURSQUARE = 'https://foursquare.com/mcman_s'
UNTAPPD = 'https://untappd.com/user/mcman_s'
## Disqus Sitename for comments on posts
## Commenting mine out for this theme site
DISQUS_SITENAME = 'brutalistpelican'
## Gravatar
## Commenting mine out so you can see how the theme looks without one
## See https://mamcmanus.com to see what it looks like with a Gravatar
# GRAVATAR = 'https://www.gravatar.com/avatar/a5544bcae63c5d56c0b7a3fa0ab5b295?s=256'
```

## Plugins
I use this theme on [my site]("https://mamcmanus.com") with the following plugin configuration.

```python
# PLUGINS
PLUGIN_PATHS = ['plugins']
PLUGINS = ['sitemap', 'category_order', 'w3c_validate', 'optimize_images', 'gzip_cache']

## SITEMAP PLUGIN
SITEMAP = {
    'format': 'xml',
    'priorities': {
        'articles': .99,
        'pages': .75,
        'indexes': .5
    },
    'changefreqs': {
        'articles': 'daily',
        'pages': 'daily',
        'indexes': 'daily'
    },
}
```

## Design and tooling choices
Some design and tooling choices I made while building this theme. Feedback welcome.

* I kept the site in a single column for now. Research shows that the optimal character count is 66 and the single column design usually lands between 50-75.
* I chose the Lato font face and only 3 font weights because I like the way it looks. I have received feedback that it may be too hard to read so I may add some weights or change it. Instead of using the google font API urls, each font weight was translated to its raw Data URI and packaged with the theme to improve loading performance. 
* Same thing for the footer icons. I used one of my favorite tools, [Grumpicon](http://www.grumpicon.com/), to properly package the fonts. I did not introduce the entire Grumpicon JS toolchain since it seems complex and I really just needed a handful of icons.
* I designed in SASS instead of CSS, mostly for the same reasons I [outlined a few years ago](https://mamcmanus.com/2016/01/14/switching-from-css-to-sass/). 
* For date and time display I am using [moment.js](https://momentjs.com/). I've been using this script for years because it is easy to get the dates and times looking exactly how you want.
* I attempted to get the tag design as close to Stack Overflow as possible.

Contributions, ideas, and general chat welcome. Feel free to reach out on Twitter or Telegram. I'll be working to add more features over the coming months.
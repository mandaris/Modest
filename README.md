# Modest
A simple Pelican theme that that attempts to integrate opengraph and schema.org tags as well as having an easy to read experience.

## Pelican Properties
`TWITTER_USERNAME`: Used to toggle information that is twitter specific.

`GITHUB_USERNAME`: Used to help with indeweb logins when twitter is not available

`FACEBOOK_PROFILES_URL`: Used to toggle information that facebook might need.

`FACEBOOK_APPID`: If you have an AppID from facebook.

`DISQUS_SITENAME`: To allow chat on the site.

`GITHUB_USERNAME`: To allow for Github authentication.

`OPEN_GRAPH_INFO`: To allow [OpenGraph](http://opengraphprotocol.org "The Open Graph protocol enables any web page to become a rich object in a social graph.") information.

`WEBMENTIONS:`: To allow the site to have [webmentions](https://webmention.io "Webmention.io is a hosted service created to easily receive webmentions on any web page."). Set to url of address (example: mandarismoore.com)

`MICROBLOG_USERNAME`: To allow you to validate your [Micro.blog](https://micro.blog "Micro.blog is a blog hosting platform with a safe community for microblogs.") account.

### EXTRA_PATH_METADATA
I use the following to make sure that all my icons are placed where I'm expecting.
```python
EXTRA_PATH_METADATA = {'extra/favicon.png': {'path': 'favicon.png'},
                       'extra/apple-touch-icon.png': {'path': 'apple-touch-icon.png'},
                       'extra/apple-touch-icon-precomposed.png': {'path': 'apple-touch-icon-precomposed.png'},
                       'extra/favicon.ico': {'path': 'favicon.ico'},}
```

## Pelican Plugins
This theme relies on the [pelican-open_graph](https://github.com/whiskyechobravo/pelican-open_graph) plugin. There are other kinds out there but I've been using this one for years.

### Pelican JSON Feed
A new version of RSS has come out that distributes the content as JSON instead of xml. You can read about the plugin on its [github page](https://github.com/andrewheiss/pelican_json_feed "Pelican plugin to add a JSON Feed file to your site.").

I have it set to toggle on when `FEED_JSON` is defined so that it matches the other feeds.

## Recommended Python-Markdown Extensions
This theme uses two markdown extensions to format the raw text into html. These need to be installed into your environment by downloading and then running the `python setup.py install` command.

### figureAltCaption
I use this to make standalone images into figures. You can read about my set up [here](https://mandarismoore.com/2018/01/finding-figures.html). As of this writing, I've still have a [pull request](https://github.com/jdittrich/figureAltCaption/pull/3) to allow reference links.

Link: https://github.com/jdittrich/figureAltCaption 

### TOC
[Python-Markdown](https://python-markdown.github.io) has a built in feature for making a [Table of Contents](https://python-markdown.github.io/extensions/toc/) and making sure that the text being generated has the correct heading levels. 


### Excerpt from pelicanconfig.py
This is what I have in my config file to control the markdown generation.

```python
MARKDOWN = {
    'extension_configs': {
        'markdown.extensions.codehilite': {'css_class': 'highlight'},
        'markdown.extensions.extra': {},
        'markdown.extensions.meta': {},
        'markdown.extensions.toc': {'baseheader': '3', 'title': 'Table of Contents'}
        'figureAltCaption':{},
    },
    'output_format': 'html5',
}
```

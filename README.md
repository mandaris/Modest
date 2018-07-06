# Modest
A simple Pelican theme that that attempts to integrate opengraph and schema.org tags as well as having an easy to read experience.

## Pelican Properties
`TWITTER_USERNAME`: Used to toggle information that is twitter specific.

`FACEBOOK_PROFILES_URL`: Used to toggle information that facebook might need.

`FACEBOOK_APPID`: If you have an AppID from facebook.

`DISQUS_SITENAME`: To allow chat on the site.

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

## Recommended Python-Markdown Extensions
This theme uses two markdown extensions to format the raw text into html. These need to be installed into your environment by downloading and then running the `python setup.py install` command.

### figureAltCaption
I use this to make standalone images into figures. You can read about my set up [here](https://mandarismoore.com/2018/01/finding-figures.html). As of this writing, I've still have a [pull request](https://github.com/jdittrich/figureAltCaption/pull/3) to allow reference links.

Link: https://github.com/jdittrich/figureAltCaption 

### mdx_downheader
I use this to downgrade the headers in the raw markdown that I write. Sure, I could just increase the headers as I write them but sometimes the text comes from different sources. You can read what I wrote about this [here](https://mandarismoore.com/2018/07/getting-mdx_downheader-to-work.html).

Link: https://github.com/cprieto/mdx_downheader

### Excerpt from pelicanconfig.py
This is what I have in my config file to control the markdown.

```python
MARKDOWN = {
    'extension_configs': {
        'markdown.extensions.codehilite': {'css_class': 'highlight'},
        'markdown.extensions.extra': {},
        'markdown.extensions.meta': {},
        'figureAltCaption':{},
        'downheader': {'levels': '2'},
    },
    'output_format': 'html5',
}
```

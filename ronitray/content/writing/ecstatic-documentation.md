+++
title="Ecstatic v0.1 Documentation"
date=2021-02-18
listed=false
[extra]
listed=false
+++

## What is Ecstatic?
Ecstatic is a static site generator. It is written in Python and makes use of, primarily, the Jinja template engine to generate a complete website. It is ideal for blogs and/or personal/company sites.

## Installing

Note: You need to have Python and git installed on your system to use ecstatic. It has been built using Python 3+, and not tested on 2.x. It may work, but please don't expect support on deprecated versions.

Once you have installed Python on your system, go ahead and clone the git repo.

```
$ git clone https://github.com/RonitRay/ecstatic.git
```

This downloads the generator as well as some boilerplate templates and sample files to get you started right away.

Before you start, there are some python dependencies you must install. I recommend using a virtual environment or pipenv within the ecstatic folder for containerization and to not affect your system in any way.

*DEVELOPER NOTE: At the moment, Jinja v3.0 and up are not supported. They have rolled out some changes to PackageLoader that break functionality for ecstatic, and unless I understand and patch it, ecstatic will not run on machines with a new version of jinja installed. Please install v2.11.3 until specified.*

```
$ pip3 install pipenv
$ pipenv shell
$ pip3 install jinja2==2.11.3
$ pip3 install datetime markdown2
```

You should now be all set.

## Folder Structure

- The drafts folder is for all posts you are working on but don't want to publish yet, written in markdown (.md) format.
- The content folder consists of all your finished blog posts or content pages. Remember to move your markdown file from drafts to content if you want to publish it.
- The templates folder allows you to create templates in HTML with some python logic as per the Jinja specification.
- The output folder will consist of the generated site, as well as any CSS in the css folder and images in the img folder that you would like to have on the site.


## Understanding Templates

Templates are a kind of skeleton that define how any page of a particular type (eg. home, article etc) is to be structured.

Templates in Jinja exist to extend static HTML and provide scope for content to be dynamically inserted into placeholder 'blocks' using Python logic. Their excellent and extensive documentation is a great resource to understand and write templates for ecstatic, or build your own wrapper around Jinja.

Out of the box, ecstatic provides 3 templates for convenience:

### The ```layout``` template

The layout template is the most basic wrapper for every page you generate. It consists of the boilerplate html head, title, meta, and body tags, and defines 2 blocks: customtitle and content, that are pretty self-descriptive.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <link rel="stylesheet" href="/css/basic.css">
    <title>{% block customtitle %} {%endblock%} | Ronit Ray</title>
</head>
<body class="container">
    {% block content %} {% endblock %}
    <br>
</body>
</html>
```

Whenever you define a new template, you can extend this layout template and not have to write this boilerplate again.

```html
{% extends "layout.html" %}
```

### The ```home``` template

The home template is used to generate your site's homepage.

You can have whatever content you want in it. At present, it includes a basic header, and a list of your blog posts, implemented as follows:

```html
<p><strong>Latest posts:</strong></p>
{% for post in posts %}
{% if post.blog == 'yes' %}
<a href="posts/{{ post.slug }}.html">{{post.title}}</a>
<br><br>
{% endif %}
{% endfor %}
```

### The `post` template

The post template defines how the html page for every blog post will be formatted. It is pretty basic, you just include {{post.content}} somewhere in the body to load the generated HTML for your markdown post.

## New Post

To create a new post, execute:

```
$ python3 new-post.py
```

You are asked to provide a title for the post, a list of comma-separated tags (optional), a post summary (optional), and a slug (the slug is used to determine the name of the markdown file as well as the URL for the post.)

You are also asked if the post is a blog post or not (optional), since you can use this flag to separate your blog posts from other static content on your site.

Generated markdown file is placed in the drafts folder.

Posts are written in Markdown. Refer to a Markdown style guide and the Python markdown2 library documentation for more. Once you are satisfied with your post, move it from the drafts folder to the content folder.

## Generate Your Site

To generate the static site, execute:

```
$ python3 generate.py
```

No prompts are provided for the generation process. It should be near instant for a reasonable number of posts. Upon completion of execution, all site-related pages and content is available in the output folder. You may push this entire folder to a server of your choice, or use GitHub Pages, GitLab Pages, Cloudflare Pages, Netlify, or Neocities for hosting if you would like. 

## Extending Ecstatic

With templates, your static site can be extended into a pretty functional site in no time without having to alter the generating program in any way. That said, if you want more functionality than just a basic blog and landing pages, you can bake it into the generate.py script. It is a standard python script and can be extended for any purpose you deem fit.

Here are some helpful extensions you might want to use. Eventual releases may include patches as separate files that you can install much like patches in dwm, but that is not implemented at present.

### Tags

Tags allow you to categorize your posts and are a pretty common feature on blogs all over the web. Ecstatic already asks you to provide an (albeit optional) comma-separated list of tags that you think are relevant to your posts. If you would like to include tag-based categorization on your blog, add the following code to your generate.py script.

```python
# extract unique list of tags and sort
tags = []
for post in posts_metadata:
    if post['blog'] == 'yes':
        tags.extend(post['tags'].split(', '))
tags = list(set(tags))
tags.sort()

# make a list of posts for each tag, then create a new page dedicated to all posts for that tag
tag_template = env.get_template('tag.html')
for tag in tags:
    tagposts_metadata = [
        POSTS[post].metadata for post in POSTS if tag in POSTS[post].metadata['tags'].split(', ')]
    tag_html = tag_template.render(tagposts=tagposts_metadata, tag=tag)
    with open('output/posts/tag-'+tag+'.html', 'w') as file:
        file.write(tag_html)            
```

This patch is already applied to ecstatic. A set of links to these generated tab pages is present on the home template: 

```html
{% for tag in tags %}
<a href=posts/tag-{{tag}}.html>[{{tag}}]</a>&nbsp;&nbsp;&nbsp;
{% endfor %}
```

If you do not want tags, you can get rid of that section of the template.

### Reading time

A reading time indicator appears typically near the top of a post, indicating the average time it might take a reader to go through the post. This patch is already applied to the generator, but it is trivial to remove (relevant sections are commented in the code) and even easier to ignore (just remove any mention of reading time from your post template).

Note: This assumes an average reading time of 200 words per minute.

```python
post_clean = POSTS[post]
for char in '-.,\n':
    post_clean = post_clean.replace(char, ' ')
post_clean = post_clean.lower()

post_words = post_clean.split()

post_data = {
.
.
.
'readtime': round(len(post_words)/200)
}      
```

### RSS Feed

RSS Feeds are XML documents that allow users to follow content posted to your site without having to visit the site itself. Users following your site via RSS feed expect to be notified in their feed reader when your site changes, which means every time you generate your site, the rss feed must also be regenerated to include any new content.

This patch is not applied to ecstatic by default, but you can add it to the generate.py script as below: 

```python
# for generating an RSS feed
filecontent = '<?xml version="1.0" encoding="utf-8"?>\n<rss xmlns:content="http://purl.org/rss/1.0/modules/content/" version="2.0">\n<channel>'
filecontent += '<!--  RSS generated by ecstatic, a minimal static site generator  -->'
filecontent += "<title>Author's Site</title>\n<link>https://url.site/</link>\n<description>Feed for Author's website</description>\n<lastBuildDate>"+ (date.today().strftime("%a, %d %b %Y")) +"</lastBuildDate>\n"

for post in POSTS:
    post_metadata = POSTS[post].metadata
    postdate=datetime.strptime(post_metadata['date'],"%d-%b-%Y")
    nowdate=datetime.strptime(date.today().strftime("%d-%b-%Y"),"%d-%b-%Y")
    daydiff = nowdate - postdate

    if daydiff.days <= 180 and post_metadata['blog']=='yes':
        filecontent+= "<item>\n"
        filecontent+= "<title>"+post_metadata['title']+"</title>\n"
        filecontent+= "<link>"+"https://url.site/posts/"+post_metadata['slug']+".html"+"</link>\n"
        filecontent+= "<pubDate>"+datetime.strptime(post_metadata['date'],"%d-%b-%Y").strftime("%a, %d %b %Y")+"</pubDate>\n"
        filecontent+= "<description>"+post_metadata['summary']+"</description>"
        filecontent+= "\n<content:encoded><![CDATA["+POSTS[post]+"]]></content:encoded>\n"
        filecontent+= "</item>\n"

filecontent+= "</channel>\n</rss>"

with open('output/feed.xml', 'w') as file:
    file.write(filecontent)

# end
```

Remember to replace https://url.site with your own domain. You may then link to url.site/feed.xml anywhere on your site to point to the RSS feed generated this way.

## Next Steps

If you find any bugs or have feature requests, feel free to raise an issue at this project's GitHub page. Not all feature requests will be implemented for the sake of simplicity but some may be provided as patches in the future.

+++
title="Tags are a thing now, I guess"
date= 2020-11-05
description="The super-basic static site generator I wrote now supports tags."
[extra]
listed=true
+++

In case you don't know, I've been writing [my own static site generator in Python](https://github.com/RonitRay/ecstatic) to generate this site. The initial codebase was borrowed with thanks from [Naveera Ashraf's very helpful blog post](https://blog.naveeraashraf.com/posts/make-static-site-generator-with-python/). I have since put in some of my own code to implement the following:

1. A homepage template with some formatting to show a bio and some relevant links aside from the blog feed. This works pretty well as a homepage for a personal site and is extensible to include fancy CSS and JS if someone is so inclined.
1. One of the features mentioned in their post was:
   >_One more thing that I want to do is to have the tags of each post in some kind of list so I can loop through them as I may want to make each tag into a clickable link_

   The way they chose to implement it was to generate the tags for each post and display them as buttons below the post, but what one did with those buttons was up to them. Which is fair, but I wanted to build a system that could pick up unique tags and generate multiple separate pages of posts relevant to each tag. This is something that would have been trivial to do with some JS filtering, but I was adamant on keeping this site static, light and JS-free until I really needed it so I wanted a workaround and wrote one.
   1. A set of unique tags is built after scanning each post.
        ```python
        python tags = []; 
        for post in posts_metadata: 
            if post['blog']=='yes': 
                tags.extend(post['tags'].split(', ')); 
        tags=list(set(tags)); 
        tags.sort();
        ```

   1. There is a 'tag' template that is meant to display all posts for a particular tag, which are passed to it by the generator.
        ```html
        {% for post in tagposts %}
        {% if post.blog == 'yes' %}
            &lt;p&gt; {{post.date}} | &lt;a href="posts/{{ post.slug }}.html"&gt;{{post.title}}&lt;/a&gt;&lt;/p&gt;
        {% endif %}
        {% endfor %}
        ```

   1. This tag page is generated in my main generator program for every unique tag. We loop through the posts, find whether their tag list contains a particular tag, and then pass it in the list of posts to the template if it does.
        ```python
        tag_template = env.get_template('tag.html')
        for tag in tags:
            tagposts_metadata = [POSTS[post].metadata for post in POSTS if tag in POSTS[post].metadata['tags'].split(', ')]
            tag_html = tag_template.render(tagposts=tagposts_metadata, tag=tag)
            with open('output/posts/tag-'+tag+'.html', 'w') as file:
                file.write(tag_html)
        ```

Since all of the generation is done on my development/writing machine, only the static output is published to the site and it loads as fast as any static HTML for the user, no unnecessary CPU hogging needed. I'm almost positive this code is suboptimal because it's literally a quick and dirty way to get what I wanted. I'll either get around to making it better later, or, well, the kids will have something a little more substantial than incorrect grammar corrections to do next Hacktoberfest.

---
tags: [A, B, 'C C C' ] 
categories: [Other, 'Long Name']
---

# Jekyll Magic

## MarkDown Parser (Kramdown)

https://kramdown.gettalong.org/quickref.html

### Adding Styling To Html Output

https://digitaldrummerj.me/styling-jekyll-markdown/





## Liquid 

Jekyll uses the Liquid templating language to process templates.

https://shopify.github.io/liquid/filters/newline_to_br/
https://jekyllrb.com/docs/liquid/

## Liquid Snippets

### TOC

https://github.com/allejo/jekyll-toc

### Tags

https://codinfox.github.io/dev/2015/03/06/use-tags-and-categories-in-your-jekyll-based-github-pages/

### WIP

```liquid 
{% raw %}
{% for page in site.pages %}
   {% if page.title %}
      {% assign dirparts = page.dir | split:"/" %}
      {% assign folder = dirparts.last | split: "/" %}
      {% assign folders = folders | concat: folder | uniq %}
   {% endif %}
{% endfor %}
{% endraw %}
```
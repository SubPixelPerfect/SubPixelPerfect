---
tags: [A, B, 'C C' ] 
---

# Jekyll Tips & Tricks

Few notes I made while making this jekyll theme.
<!--cut-->

## Live coding using live.js

[Live.js](http://livejs.com/) makes sure you're always looking at the latest version of the page you're working on.

When includes Live.js monitors the current page including local CSS and JavaScript by sending consecutive HEAD requests to the server. Changes to CSS will be applied dynamically and HTML or JavaScript changes will reload the page.

Obviously it has to be disabled on production, this can be done using `jekyll.environment` variable


The default value for `JEKYLL_ENV` is `development`. 
GitHub Pages sets the `JEKYLL_ENV` to `production`.

So to make live.js work only in development environment include it this way:

{% raw %}
```html
{% if jekyll.environment == "development" %}
    <script type="text/javascript" src="http://livejs.com/live.js"></script>
{% endif %}
```
{% endraw %}



## MarkDown Parser (kramdown)

Jekyll uses [kramdown](https://kramdown.gettalong.org/) to convert markdown to html.

[kramdown syntax reference](https://kramdown.gettalong.org/syntax.htm)


By default GitHub Pages has kramdown.hard_wrap option set to `false` 
This means that new lines on .md file going to be converted to white space

Setting it to `true` will tell parser to replace newlines with `<br/>`
You can do it in `_config.yml` file
```yml
# Markdown renderer config 
kramdown:
  hard_wrap: true
```

More karmdown config options can be found [here](https://kramdown.gettalong.org/options.html)


### Markdown extensions

Besides support for [standard markdown](https://www.markdownguide.org/basic-syntax), karmdown extends markdown syntax

For example you can define html tag attributes 



```
> Blockquote
{:#q-id.q-class1.q-class2 title="Q Title" custom-data="data" }
```
```html
<blockquote id="q-id" class="q-class1 q-class2" title="Q Title" custom-data="data">
  <p>Blockquote</p>
</blockquote>
```



Or something more complex

```
- {:.li-class} [Link1](#){:.a-class custom-data="data1" }
- {:.li-class} [Link2](#){:.a-class custom-data="data2" }
{:#cool-list.ul-class}
```
```html
<ul id="cool-list" class="ul-class">
  <li class="li-class"><a href="#" class="a-class" custom-data="data1">Link1</a></li>
  <li class="li-class"><a href="#" class="a-class" custom-data="data2">Link2</a></li>
</ul>
```

or even this  
```
{: style="background:#123; padding:1.5em; border-radius:10px; text-align:center;"}
This paragraph styles defined with markdown
```

{: style="background:#123; padding:1.5em; border-radius:10px; text-align:center;"}
Tis paragraph styles defined with markdown



or [Material Icons](https://material.io/tools/icons/?icon=bookmarks&style=baseline)

```
_face_{:.material-icons} _link_{:.material-icons} _label_{:.material-icons}  
```

_face_{:.material-icons} _link_{:.material-icons} _label_{:.material-icons}  



### ToC
```
- 
{:toc}
```

- 
{:toc}


### Disable karmdown
```
{::nomarkdown} 
   #### This in not goinng to be converted to <h4>
{:/}
```



## Liquid 

Jekyll uses the Liquid templating language to process templates.

[Liquid Syntax Reference](https://shopify.github.io/liquid/filters/newline_to_br/)
[Jekyll Liquid Syntax Reference](https://jekyllrb.com/docs/liquid/)
[Cheatsheet](https://devhints.io/jekyll)

## Liquid Snippets

### TOC

https://github.com/allejo/jekyll-toc

### Tags

https://codinfox.github.io/dev/2015/03/06/use-tags-and-categories-in-your-jekyll-based-github-pages/



### While Loop

While loops not present in liquid but you can do following:

```liquid
{% raw %}
{% for i in (0..1000000000) %} 
    {%- if i == 5 -%}{% break  %}{%- endif -%}
    {{i}}
{% endfor %}
{% endraw %}
```


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

## 

## Markdown 

[Basic Syntax](https://www.markdownguide.org/basic-syntax)
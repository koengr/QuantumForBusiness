---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

# layout: home
---
Hello, this is a test. This seems to be the index page. 

- [page1](page1)
- [page2](page2)

## List of posts 1?

 <ul class='post-list'>
    {% for dir in site.collections %}
      {% assign collection = dir.label %}
      {% for page in site[collection] %}
        <li>
          <h2> <a href="{{ page.url | prepend: site.baseurl }}">{{ page.title }}</a> </h2>
          <small>{{ page.date | date: "%b %-d, %Y" }}</small>
        </li>
      {% endfor %}
    {% endfor %}
  </ul>

## List of posts by category?
<ul>
{% for category in site.categories %}
  <li><a name="{{ category | first }}">{{ category | first }}</a>
    <ul>
    {% for post in category.last %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
    </ul>
  </li>
{% endfor %}
</ul>
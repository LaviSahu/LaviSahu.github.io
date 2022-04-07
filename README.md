## Welcome 

This is 

<h1>{{ page_title }}</h1>

<ul>
  {%- for article in blog.articles -%}
    <li>

      <h2>
        <a href="{{ article.url }}">

          {%- if article.image -%}
            <img src="{{ article.image | img_url: '300x300' }}" alt="">

            <noscript>
            <p>
              {{ article | img_url: '455x300', scale: 2 | img_tag: article.title }}
            </p>
            </noscript>
          {%- endif -%}

          {{ article.title }}
        </a>
      </h2>

      {%- if section.settings.blog_show_author -%}
        <span>
          By {{ article.author }}
        </span>
      {%- endif -%}

      {%- if section.settings.blog_show_date -%}
        <span>
          {{ article.published_at | time_tag: format: 'month_day_year' }}
        </span>
      {%- endif -%}

      <p>
        {%- if article.excerpt.size > 0 -%}
          {{ article.excerpt }}
        {%- else -%}
          {{ article.content | strip_html | truncate: 150 }}
        {%- endif -%}
      </p>

      {%- if article.tags.size > 0 -%}
        <ul>
          {{ 'blogs.article.posted_in' }}
            <li>
              {%- for tag in article.tags -%}
                <a href="{{ blog.url }}/tagged/{{ tag | handle }}">{{ tag }}</a>{% unless forloop.last %}, {% endunless %}
              {%- endfor -%}
            </li>
        </ul>
      {%- endif -%}

      <ul>
        <li>
          <a href="{{ article.url }}" aria-label="Read more: {{ article.title }}">
            Read more
          </a>
        </li>
        {%- if blog.comments_enabled? and article.comments_count > 0 -%}
          <li>
            <a href="{{ article.url }}#comments">
              {{ article.comments_count }}
            </a>
          </li>
        {%- endif -%}
      </ul>

    </li>
  {%- endfor -%}
</ul>

{% schema %}
{
  "name": "Blog pages",
  "settings": [
    {
      "type": "checkbox",
      "id": "blog_show_author",
      "label": "Show author",
      "default": true
    },
    {
      "type": "checkbox",
      "id": "blog_show_date",
      "label": "Show date",
      "default": true
    }
  ]
}
{% endschema %}

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/LaviSahu/LaviSahu.github.io/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.

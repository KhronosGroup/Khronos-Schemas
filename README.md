# Khronos Schemas

This repository backs the website https://schema.khronos.org/. Changes merged to `main` are automatically built and deployed via GitHub Actions to AWS S3 and served through CloudFront.

## Adding a new directory

1. Create the directory and add your schema files inside it.
2. Create an `index.md` file in the new directory with the following content (replace `your-directory` and `Your Title`):

```markdown
---
layout: default
title: Your Title
---
<ul>
{% directory path: your-directory exclude: md %}
<li><a href="{{ file.url }}">{{ file.name }}</a></li>
{% enddirectory %}
</ul>
```

3. Commit and push. The site will deploy automatically.

## Local development

Run a local Jekyll build and serve the site:

```
bundle exec jekyll serve
```

Then open http://localhost:4000 in your browser. The site rebuilds automatically when files change.

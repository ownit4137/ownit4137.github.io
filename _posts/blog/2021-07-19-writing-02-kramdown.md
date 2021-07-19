---
layout: post
title: How to write contents 2
categories: [Blog]
published: true

hide_last_modified: true
# related_posts:
#   - /_posts/blog/2021-01-01-writing-01-markdown.md
# image: '/assets/img/categories/pytorch.png'
# accent_image: 
#   background: url('/assets/img/categories/pytorch.png') center no-repeat
#   overlay: false
accent_color: '#ccc'
theme_color: '#ccc'

invert_sidebar: false
---

# How to write contents 2

How to write contents using kramdown

1. toc
{:toc}


## Table of content
- Use `{:toc}`, and if you want toc to be showed in large displays, use `.large-only`

```
* unordered toc
{:toc} 

1. ordered toc
{:toc}
```

## Message box

`{:.message}`

**NOTE**: You can add a message box.
{:.message}


## Note

`{:.note title="title"}`

This is a note.
{:.note}

This is a note with title.
{:.note title="Caution"}


## Large text

`{:.lead}`

You can add large text.
{:.lead}

> You can add large quote.
{:.lead}


## Faded text

`{:.faded}`

I'm faded.
{:.faded}


## Abbreviation

- Abbreviation, like HTML should be defined like `*[HTML]: HyperText Markup Language`.
- You can see the words it stands for if you click abbreviations. HTML

*[HTML]: HyperText Markup Language


## Link

- Link should be used like `[Blog]: /`.
- Like [Blog]

[blog]: /


## Footnote

- Footnote should[^1] be used like `[^1]: foo`

[^1]: bar.


## Image
- `{:style='width:2a%;margin:0% 50-a%;' loading='lazy'}`
- `{:.figcaption}`

![Full-width image](/assets/img/categories/pytorch.png){:style='width:20%;margin:0% 40%;' loading='lazy'}

A caption to an image.
{:.figcaption}


## Code

~~~js
// file: "code-block.js"

// file: "code-block.js"

var adder = new Function("a", "b", "return a + b");

adder(2, 6);
// > 8
~~~


```html
<!-- file: `_includes/my-body.html` -->

<!-- file: `_includes/my-body.html` -->

<script type="module">
  document.querySelector("hy-push-state").addEventListener("hy-push-state-load", () => {
    const supportsCodeHighlights = false; // TBD!!
  });
</script>
```

## Table


#### Basic table

| Default aligned |Left aligned| Center aligned  | Right aligned  |
|-----------------|:-----------|:---------------:|---------------:|
| First body part |Second cell | Third cell      | fourth cell    |


#### Transposed table

`{:.flip-table}`

| Default aligned |Left aligned| Center aligned  | Right aligned  |
|-----------------|:-----------|:---------------:|---------------:|
| First body part |Second cell | Third cell      | fourth cell    |
{:.flip-table}


#### Stretched table

`{:.stretch-table}`

| Default aligned |Left aligned| Center aligned  | Right aligned  |
|-----------------|:-----------|:---------------:|---------------:|
| First body part |Second cell | Third cell      | fourth cell    |
{:.stretch-table}


#### Large table
 
`{:.scroll-table}`

| Default aligned |Left aligned| Center aligned  | Right aligned  | Default aligned |Left aligned| Center aligned  | Right aligned  | Default aligned |Left aligned| Center aligned  | Right aligned  | Default aligned |Left aligned| Center aligned  | Right aligned  |
|-----------------|:-----------|:---------------:|---------------:|-----------------|:-----------|:---------------:|---------------:|-----------------|:-----------|:---------------:|---------------:|-----------------|:-----------|:---------------:|---------------:|
| First body part |Second cell | Third cell      | fourth cell    | First body part |Second cell | Third cell      | fourth cell    | First body part |Second cell | Third cell      | fourth cell    | First body part |Second cell | Third cell      | fourth cell    |
| Second line     |foo         | **strong**      | baz            | Second line     |foo         | **strong**      | baz            | Second line     |foo         | **strong**      | baz            | Second line     |foo         | **strong**      | baz            |
| Third line      |quux        | baz             | bar            | Third line      |quux        | baz             | bar            | Third line      |quux        | baz             | bar            | Third line      |quux        | baz             | bar            |
| Second body     |            |                 |                | Second body     |            |                 |                | Second body     |            |                 |                | Second body     |            |                 |                |
| 2 line          |            |                 |                | 2 line          |            |                 |                | 2 line          |            |                 |                | 2 line          |            |                 |                |
| Footer row      |            |                 |                | Footer row      |            |                 |                | Footer row      |            |                 |                | Footer row      |            |                 |                |
{:.scroll-table}


---
layout: post
title: How to write contents 1
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

# How to write contents 1

How to write contents using markdown


## Inline Markdown elements

- **To bold text**, use `**To bold text**`.
- *To italicize text*, use `*To italicize text*`.

> This
>
> is quotation.

```
Single                    code              line                                    with                                                   scroll
```


## Inline HTML elements

- Citations, like <cite>&mdash; Mark otto</cite>, should use `<cite>&mdash;`.
- ~~Deleted~~ text should use `~~deleted~~` and <ins>inserted</ins> text should use `<ins>`.
- Superscript <sup>text</sup> uses `<sup>` and subscript <sub>text</sub> uses `<sub>`.
- <a href="#">Linked</a> text uses `<a>` or `[Linked](link)`.


## Heading 2
This is Heading 2

### Heading 3
This is Heading 3

#### Heading 4
This is Heading 4

##### Heading 5
This is Heading 5

###### Heading 6
This is Heading 6


## Code

> ~~~
>
> ruby, c, cpp, java, python, go
>
> html, css, js
>
> md, json, sql, xml
>
> make, sh


~~~js
var adder = new Function("a", "b", "return a + b");

adder(2, 6);
// > 8
~~~

### Code with filename


## Lists

* This
* is
* an unordered list

1. This
2. is
3. an ordered list

## Definition

You can explain the word by using `:` in front of the definition.
{:.faded}

Cascading Style Sheets (CSS)
: Used to describe the appearance of Web content

JavaScript (JS)
: The programming language used to build advanced Web sites and applications

## Images


### Small image

![](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f1/Heart_coraz%C3%B3n.svg/160px-Heart_coraz%C3%B3n.svg.png)

### Large image

![](/assets/img/categories/pytorch.png)



## Tables

**Basic table**

| Name     | Upvotes   | Downvotes |
|:---------|:----------|:----------|
| Alice    |        10 |        11 |
| Bob      |         4 |         3 |
| Charlie  |         7 |         9 |
|==========|===========|===========|
|Totals    |        21 |        23 |

**In markdown**

~~~md
| Name     | Upvotes   | Downvotes |
|:---------|:----------|:----------|
| Alice    |        10 |        11 |
| Bob      |         4 |         3 |
| Charlie  |         7 |         9 |
|==========|===========|===========|
|Totals    |        21 |        23 |
~~~


### Horizontal line

* * *

`* * *`


### And a nested list:

- level 1
  - level 2
    - level 3
    - level 3
  - level 2


## Math
`$$`

$$
\begin{aligned}
  \phi(x,y) &= \phi \left(\sum_{i=1}^n x_ie_i, \sum_{j=1}^n y_je_j \right) \\[2em]
            &= \sum_{i=1}^n \sum_{j=1}^n x_i y_j \phi(e_i, e_j)            \\[2em]
            &= (x_1, \ldots, x_n)
               \left(\begin{array}{ccc}
                 \phi(e_1, e_1)  & \cdots & \phi(e_1, e_n) \\
                 \vdots          & \ddots & \vdots         \\
                 \phi(e_n, e_1)  & \cdots & \phi(e_n, e_n)
               \end{array}\right)
               \left(\begin{array}{c}
                 y_1    \\
                 \vdots \\
                 y_n
               \end{array}\right)
\end{aligned}
$$


## Include markdown file

- You can include markdown file in `/_includes` folder by using `{&#37; include filename &#37;}`
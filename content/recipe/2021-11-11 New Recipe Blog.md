---
title: New Recipe Blog 
date: '2021-11-11'
categories:
  - Tutorial
description: A brief tutorial on how to use Hugo to make a website
slug: new-recipe-blog
toc: false
draft: true
---

The rendering of the page into HTML is controlled by the `layouts/_default/single.html` template, which uses the files `layout/partials/` to generate the top (and very bottom) of this (and all) pages. 
All of this can be changed to whatever you want.
To make an aesthetically pleasing website, cascading style sheets (CSS) are used to render the HTML on the viewer's browser in a certain way.
CSS specifies rules for how HTML should look, and the rules for this blog are in `static/css/style.css`.
All visual components are set there - without the raw HTML will be page-spanning paragraphs using browser default style (usually black text on white background).

## Text auto-layout

Markdown (`.md`) is a simple language for storing content and hints for how to format it.
The actual formatting is done by Hugo after reading the markdown when converting it to HTML.
Markdown translates directly into HTML, but HTML is much harder to write by hand.

## Metadata

The part above in the 
```
---
[stuff here]
---
```
block is metadata for this page, and not strictly speaking markdown.
Most parts are self explanatory, except:
* `slug` - how this page is put into a URL (`https://lynns.recipes/recipe/[slug]`)
* `toc` - headings above level 4 will be rendered into a clickable table of contents at the top
* `draft` - a `draft: true` page will only be shown on your local development site, and not deployed to the web.


## Typesetting

Typically, I start new sentences on new lines, because git tracks changes line-by-line (not required).
Some people will prefer to make sure no lines go past 80 chars and add breaks
arbitrarily to enforce this (not required).
Most line breaks are ignored, but two line breaks make a new paragraph.
All lines not separated by an empty line will be joined into a single paragraph.
Feel free to put all lines from a paragraph on the same line.

This starts a new paragraph.
This continues the paragraph.

## Subheadings

### Sub-subheadings

#### Etc.

The top level heading (a single #) is generated with the title metadata at the top.
The style of the heading is controlled by `style.css`.

## Formatting

**Bold** _itallics_ *also itallics* `literal`

* an
* unordered
* list
* of 
* items

1. numbered
1. lists
8. are
27. auto-numbered
1. !!!

- can
- also
- use
- dashes
  * nest with two spacees before dash or astrix
    - can go as deep as you want
      * common to alternate dash/astrix for levels, not required
  * style once again comes from `style.css`

## Images

The most robust way is to use `figure` shortcodes, which are things contained in {{&lt; &gt;}} tags.
These lookup bits of HTML in the `layout/shortcodes/` (or in the case of `figure`, included with Hugo), and insert them into the HTML at the appropriate spot.
The figure `class`es in the `style.css` control how text is wrapped and the size/position of the figure.
The `src` tag is a path within the `static/` directory to the desired picture.

{{< figure src="images/placeholder.jpg" caption="Captions are optional, but this is what they look like." class="center" >}}

## Links

Links specify displayed text and a URL to redirect to.
These can be URLs within the site (omit the domain name, start with the first slash after the domain) or external.
For instance, [here is a link to Hugo markdown documentation](https://www.markdownguide.org/tools/hugo/) which will show how to do more complicated typesetting, if necessary.





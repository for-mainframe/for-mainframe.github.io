---
id: home
layout: default
title: Home
permalink: /
---

# IJMP projects documentation repo
This repo is intended to provide documentation for every publicly available IJMP project

## Requirements for development environment
Install Ruby latest version.
After Ruby is installed, run:
```
bundle install
```

## How to run
```
bundle exec jekyll serve
```

## Useful links
Jekyll: https://jekyllrb.com/

Liquid: https://shopify.github.io/liquid/

## If you want to add content
You have two choices: create a single file or create a folder with related pages.
In case you created a folder with the content for the specified tool/project, it is highly recommended to have 'index.md' as the product main page.
To create a new page, you need to create a Markdown file with such contents:
```
---
id: <page-id>
layout: default
title: <page-title>
permalink: /<page-link>/
---
```
- ``<page-id>`` - ID for the page. It will be used in sidebar section
- ``<page-title>`` - the page title
- ``<page-link>`` - the page link

After the page is filled with content, 'sidebar.yml' should be changed as follows:
```
- section_name: <section-name>
  section_id: <section-id>
  section_items:
  - id: <page-id>
    name: <section-item-name>
```
- ``<section-name>`` - section name to display
- ``<section-id>`` - section ID
- ``<page-id>`` - page ID to get URL by that ID
- ``<section-item-name>`` - the name of the section item

And also there should be changes in 'contents.yml':
```
- page_id: <page-id>
  page_contents:
    - name: <content-section-name>
      section: <content-section-link>
    <other sections if needed>
```
- ``<page-id>`` - page ID to get contents by that ID
- ``<content-section-name>`` - the name of the section on the page
- ``<content-section-link>`` - the link to the section on the page. Usually it would be kebab-cased name of the section, marked with '#' (e.g.: section name: For Mainframe => section link: for-mainframe ).

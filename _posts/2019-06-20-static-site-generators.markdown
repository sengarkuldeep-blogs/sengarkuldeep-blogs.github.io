---
layout: post
title: 'Static Site Generators'
date: 2019-06-20
categories: jekyll
---

Static site generators are tools that generate static web pages/site from a very simple and expressive source. 

<!-- more -->
With static site generators you can:
- Keep your content and design separately. 
- Either choose an available theme, customize them or create it from scratch. 
- Deploy them to any web server that can serve static data, a great and widely used example is github pages. 

There are many site generators for building photo galleries like [Expose](https://github.com/Jack000/Expose), for writing documentations like [gitbook](https://www.gitbook.com/), and [many more](https://www.staticgen.com/). 


## Why do we need them

1. **Performance**: 

    A dynamic cms, like wordpress, processes and generate resource for every single resource. Processing may require accessing various server resources like databases. Whereas web site generated from static site generators are static files and require no extra processing. 
2. **Versioning**:

    With static site generators we can version our posts using any standard VCS, whereas with dynamic cms, your pages are hardly versioned (may be by creating backups).

3. **Intuitive**:

    Site generators is a more intuitive way of writing posts, documenations and web sites. 

4. **Flexibility**: 

    Using markup language like *markdown* provides great flexibilty to the writers to manage the content. Writers can later choose to create pdfs or mobi books from markdown using markdown converters like [pandoc](https://pandoc.org/)

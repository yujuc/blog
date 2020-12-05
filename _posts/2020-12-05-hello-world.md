---
layout: post
title: "Hello World"
date: 2020-12-05 16:00:00 +0900
categories: random en
---

## What is this blog for?

Just for recording my life, my thought, my notes (language, programming, travelling... etc).

## Why I built this blog?

Actually I tried different blog platform before, like Blogger, Logdown, Medium, WordPress, even PTT2 (only Taiwanese know 😏). But I'm not really very active because the "writing cost" is too high, like logging into the platform, formatting the style, finding some nice photos etc. Then I realized, maybe using Github Pages can reduce the cost of "start writing". Let's see if I can keep working on this 😉.

## How I built this blog
Briefly record how I built this site. Actually it takes me more time than I expected...

### STEP1: Make a simple blog with Jekyllrb
Follow the [Quickstart](https://jekyllrb.com/docs/). And it already looks nice (without knowing anything about Ruby 😁 ). 

### STEP2: Adjust to the style of "no style, please"
Mainly Follow this [instrction](https://jekyll-themes.com/no-style-please/#github-pages-installation)). But I slightly modified some steps:

- In `Gemfile`
    - Add `gem "no-style-please", "~> 0.3.1"`
    - Modify `gem "jekyll", "~> 3.8.7"`
- Add `theme: no-style-please` to the file `_config.yml`
- Run `bundle`
    
I assigned the version of "no-style-please" to Gemfile, because the default version is 0.1.0, which doesn't apply the latest change. And the Jekyll version also has to be changed accordingly.

### STEP3: Custimize your menu 
Create `_data/menu.yml`. I refer to the [sample](https://github.com/riggraz/no-style-please/blob/master/_data/menu.yml) from the author

### STEP4: Overwrite the defaul layout
The default templates perform slightly different. So I added this two files
Adding two files

- `_includes/menu_item.html`
- `_includes/post_list.html`

 Actually I also copied from the author's github　😛

### STEP5: Create archive pages
This is the page when you click something like "Read More...". First you need the html as a template, then a markdown file will actually create the archive page.

- `_layout/archive.html`
- `archive.md`

### STEP6: Push to Github and enable Github Page
Follow Github Page instruction. But be aware the environment different between local and Github! Locally, the host name is `localhost:4000`, so everything starts from the root. But in Github pages, the host name will be `[account].github.io/[repo]`, which has a subdomain. For adjusting this problem, make sure to add the following code in `_config.yml`
```
url: "https://yujuc.github.io/blog"
baseurl: "/blog"
```
Also for using non-github theme, the `remote` argument should also be change to `remote_theme`
```
remote_theme: riggraz/no-style-please
``` 

### STEP7 (Optional): Add github-pages gem
As the problem I mentioned in STEP6, the root of domain might be different. If you want to always check your post locally before pushing to Github, the plugin of github-pages might solve this problem. For more details, please check the [Jekllrb Doc for Github Pages](https://jekyllrb.com/docs/github-pages/#the-github-pages-gem)!


## Reference & Acknowledgement
- [Github Pages](https://pages.github.com/)
- [Jekyllrb](https://jekyllrb.com/)
- [Not Style Please](https://jekyll-themes.com/no-style-please/)

### Other Resources
- [Tutorial](http://jmcglone.com/guides/github-pages/)
- [Jekllrb Doc for Github Pages](https://jekyllrb.com/docs/github-pages/)

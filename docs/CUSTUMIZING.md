# Customizing

## Gem-based method

With Gem-based themes, directories such as the `assets`, `_layouts`, `_includes`, `_data` and `_sass` are stored in the theme’s gem, hidden from your immediate view. Yet all of the necessary directories will be read and processed during Jekyll’s build process.

## Configuration variables

`Ex` will respect the following variables, if set in your site's `_config.yml`:
```yml
title: [The title of your site]
description: [A short description of your site's purpose]
```

Additionally, you may choose to set the following optional variables:
```yml
google_analytics: [Your Google Analytics tracking ID]
```

## Navigation and Sidebar

Customize site navigational links through a Jekyll data file. To define these links add titles and URLs under variables in `_data/navigation.yml`:
```yml
- title: About
  link: "#about"
- title: Markdown
  link: "#markdown"
```

With sidebar, variables in `_data/sidebar.yml`:
```yml
- title: "#about"
- title: "#markdown"
```

## Stylesheet

If you'd like to add your own custom styles:
1. Create a file called `/assets/css/style.scss` in your site
2. Add the following content to the top of the file, exactly as shown:
    ```scss
    ---
    ---
    @import "";
    ```

3. Add any custom CSS (or Sass, including imports) you'd like immediately after the `@import` line

*Note: If you'd like to change the theme's Sass variables, you must set new values before the `@import` line in your stylesheet.*

## Layouts

### Default layout

There’s not much to this layout apart from pulling in several `_includes`:
- `<head>`
- `<header>`
- `<navigation>`
- `{{ content }}`
- `<footer>`

Default layout loads all post in `_post` and push them into single page. See `optional variables of post` in [Working with Post](#working-with-posts) use to config default layout.

If you'd like to change the theme's HTML layout:
1. [Copy the original template](https://github.com/AREA44/jekyll-ex/blob/main/_layouts/default.html) from the theme's repository<br/>(*Pro-tip: click "raw" to make copying easier*)
2. Create a file called `/_layouts/default.html` in your site
3. Paste the default layout content copied in the first step
4. Customize the layout as you'd like

For more information, see [the Jekyll variables documentation](https://jekyllrb.com/docs/variables/).

## Woking with Posts

Posts are stored in the `_posts` directory and named according to the `YEAR-MONTH-DAY-title.MARKUP` format as per [the usual](https://jekyllrb.com/docs/posts/).

Optinal variables of post:
```yml
---
title: [The title of post]
background-color: [The background color] #default variable is "#fff"
textcolor: [The text color] #default variable is "#111"
---
```
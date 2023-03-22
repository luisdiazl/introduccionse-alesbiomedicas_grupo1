# Introducción a Señales Biomédicas Grupo 1

Repositorio del curso Introducción a Señales Biomédicas

Integrantes:  <br />
- Luis Daniel Jesús Diaz Leguizamon <br />
- Giancarlo Arian Guarnizo Bellido <br />
- Diego Fernando Segura Contreras <br />
- Alexys Caytano Melendez <br />
- Nicolle Muñoz Huamán <br />
- Yereli García Palomino <br />

Presentacion de los integrantes

## Contenido del curso a desarrollar

## Materiales a usar


Skip to content
Search or jump to…
Pull requests
Issues
Codespaces
Marketplace
Explore
 
@diegosegura23 
pages-themes
/
merlot
Public
Fork your own copy of pages-themes/merlot
Code
Issues
5
Pull requests
3
Actions
Security
Insights
Update README.md
 master
@parkr
parkr committed on Jul 26, 2021 
1 parent bd03416
commit fb604c4
Showing 1 changed file with 15 additions and 8 deletions.
  23  
README.md
Comment on this file
@@ -1,6 +1,6 @@
# The Merlot theme

[Build Status](https://github.com/pages-themes/merlot/actions/workflows/ci.yaml) [![Gem Version](https://badge.fury.io/rb/jekyll-theme-merlot.svg)](https://badge.fury.io/rb/jekyll-theme-merlot)
[![.github/workflows/ci.yaml](https://github.com/pages-themes/merlot/actions/workflows/ci.yaml/badge.svg)](https://github.com/pages-themes/merlot/actions/workflows/ci.yaml) [![Gem Version](https://badge.fury.io/rb/jekyll-theme-merlot.svg)](https://badge.fury.io/rb/jekyll-theme-merlot)

*Merlot is a Jekyll theme for GitHub Pages. You can [preview the theme to see what it looks like](http://pages-themes.github.io/merlot), or even [use it today](#usage).*

@@ -13,7 +13,9 @@ To use the Merlot theme:
1. Add the following to your site's `_config.yml`:

    ```yml
    theme: jekyll-theme-merlot
    remote_theme: pages-themes/merlot@v0.2.0
    plugins:
    - jekyll-remote-theme # add this line to the plugins list if you already have one
    ```

2. Optionally, if you'd like to preview your site on your computer, add the following to your site's `Gemfile`:
@@ -36,7 +38,7 @@ description: [A short description of your site's purpose]
Additionally, you may choose to set the following optional variables:

```yml
show_downloads: ["true" or "false" to indicate whether to provide a download URL]
show_downloads: ["true" or "false" (unquoted) to indicate whether to provide a download URL]
google_analytics: [Your Google Analytics tracking ID]
```

@@ -60,10 +62,15 @@ If you'd like to add your own custom styles:

If you'd like to change the theme's HTML layout:

1. [Copy the original template](https://github.com/pages-themes/merlot/blob/master/_layouts/default.html) from the theme's repository<br />(*Pro-tip: click "raw" to make copying easier*)
2. Create a file called `/_layouts/default.html` in your site
3. Paste the default layout content copied in the first step
4. Customize the layout as you'd like
1. For some changes such as a custom `favicon`, you can add custom files in your local `_includes` folder. The files [provided with the theme](https://github.com/pages-themes/merlot/tree/master/_includes) provide a starting point and are included by the [original layout template](https://github.com/pages-themes/merlot/blob/master/_layouts/default.html).
2. For more extensive changes, [copy the original template](https://github.com/pages-themes/merlot/blob/master/_layouts/default.html) from the theme's repository<br />(*Pro-tip: click "raw" to make copying easier*)
3. Create a file called `/_layouts/default.html` in your site
4. Paste the default layout content copied in the first step
5. Customize the layout as you'd like

### Customizing Google Analytics code

Google has released several iterations to their Google Analytics code over the years since this theme was first created. If you would like to take advantage of the latest code, paste it into `_includes/head-custom-google-analytics.html` in your Jekyll site.

### Overriding GitHub-generated URLs

@@ -106,4 +113,4 @@ If you'd like to preview the theme locally (for example, in the process of propo

### Running tests

The theme contains a minimal test suite, to ensure a site with the theme would build successfully. To run the tests, simply run `script/cibuild`. You'll need to run `script/bootstrap` one before the test script will work.
The theme contains a minimal test suite, to ensure a site with the theme would build successfully. To run the tests, simply run `script/cibuild`. You'll need to run `script/bootstrap` once before the test script will work.
0 comments on commit fb604c4
@diegosegura23
 
Add heading textAdd bold text, <Ctrl+b>Add italic text, <Ctrl+i>
Add a quote, <Ctrl+Shift+.>Add code, <Ctrl+e>Add a link, <Ctrl+k>
Add a bulleted list, <Ctrl+Shift+8>Add a numbered list, <Ctrl+Shift+7>Add a task list, <Ctrl+Shift+l>
Directly mention a user or team
Reference an issue, pull request, or discussion
Add saved reply
Leave a comment
Ninguno archivo selec.
Attach files by dragging & dropping, selecting or pasting them.
Styling with Markdown is supported
 You’re not receiving notifications from this thread.
Footer
© 2023 GitHub, Inc.
Footer navigation
Terms
Privacy
Security
Status
Docs
Contact GitHub
Pricing
API
Training
Blog
About
Update README.md · pages-themes/merlot@fb604c4

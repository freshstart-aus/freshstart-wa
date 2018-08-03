# freshstart-wa

This is the code repository for the [FreshStart development web site](https://freshstart-aus.netlify.com/). Changes made here automatically propagate to the development website a few moments after they are committed.

See the [existing website](http://www.freshstart.org.au/).

See [Up and running with blogdown](https://apreshill.rbind.io/post/up-and-running-with-blogdown/) for a guide.

## freshstart-aus repository

The freshstart-aus repository is associated with the webmaster@freshstart.org.au email address. Development of the web site takes place under the [freshstart-aus/freshstart-wa]() repository.

# Miscellaneous instructions

## Clone fresh-start repository to local Linux machine

`cd ~/Keep/www/freshstart.org.au/`

`git clone https://github.com/freshstart-aus/freshstart-wa.git`

There is now a `freshstart-wa` directory under `~/Keep/www/freshstart.com.au/`.

## Create new R project

Use the top menu buttons in RStudio to select File -> New Project -> Existing Directory, browse to the `freshstart-wa` directory, then click on the Create Project button.

Edit `.gitignore` to ignore certain files (e.g. .html).

## Create new site using blogdown

`blogdown::new_site(theme = "devcows/hugo-universal-theme", theme_example = TRUE)`

(Had to move Readme.md and .html to another place before doing this.)

Uncheck a couple of [project options](https://bookdown.org/yihui/blogdown/rstudio-ide.html#fig:project-options).

## Push to GitHub

```
tjf2n@TJF:~/Keep/www/freshstart.com.au/freshstart-wa$ 
git add *
git commit -m "foo"
git push https://github.com/freshstart-aus/freshstart-wa
```

## Deploy with Netlify

Go to Netlify and [deploy](https://app.netlify.com/sites/freshstart/deploys). This assumes that Netlification has already been done.

## Set up a new Hugo site

Set up a Hugo site as per instructions at [https://gohugo.io/getting-started/](https://gohugo.io/getting-started/).

```cd ~/Keep/www/freshstart.com.au/```

```hugo new site freshstart```

### Initialize Git

```cd freshstart```

```git init```

### Add a theme

```cd themes```

```git clone https://github.com/SteveLane/hugo-icon.git```

```cd ..```

```cp themes/hugo-icon/exampleSite/config.toml .```

### Add a post

```hugo new posts/my-first-post.md```

### Run server

```hugo server -D```

## HUGO XMIN

### _Keep it simple, but not simpler_

**XMin** is a Hugo theme written by [Yihui Xie](https://yihui.name) in about four hours: half an hour was spent on the Hugo templates, and 3.5 hours were spent on styling. The main motivation for writing this theme was to provide a really minimal example to beginners of Hugo templates. This XMin theme contains about 130 lines of code in total, including the code in HTML templates and CSS (also counting empty lines).


```bash
find . -not -path '*/exampleSite/*' \( -name '*.html' -o -name '*.css' \) | xargs wc -l
```

```
       5 ./layouts/404.html
      18 ./layouts/_default/list.html
      12 ./layouts/_default/single.html
      16 ./layouts/_default/terms.html
       0 ./layouts/partials/foot_custom.html
       9 ./layouts/partials/footer.html
       0 ./layouts/partials/head_custom.html
      20 ./layouts/partials/header.html
       7 ./static/css/fonts.css
      50 ./static/css/style.css
     137 total
```

I can certainly further reduce the code, for example, by eliminating the CSS, but I believe a tiny bit CSS can greatly improve readability. You cannot really find many CSS frameworks that only contain 50 lines of code.

[![Screenshot](https://github.com/yihui/hugo-xmin/raw/master/images/screenshot.png)](https://xmin.yihui.name)

## Blogdown

See [Making websites with R Markdown](https://www.rstudio.com/resources/webinars/introducing-blogdown/) and [blogdown: Creating Websites with R Markdown](https://bookdown.org/yihui/blogdown/).

### Install blogdown

`install.packages("devtools")`

`devtools::install_github('rstudio/blogdown')`

### Create new site

* Make a directory: `mkdir ~/Keep/www/freshstart.com.au/mk1`

* Create a new project using the directory just made.

* Create a new site: `blogdown::new_site()`

The new site can be created with a particular theme too: `blogdown::new_site(theme = 'vjeantet/hugo-theme-docdock')`

Alternatively, install a theme after creating the new site: `blogdown::install_theme('jbub/ghostwriter')`

# easy-jekyll-starter

[![Deploy to GitHub Pages](https://github.com/mattxwang/easy-jekyll-starter/actions/workflows/gh-deploy.yml/badge.svg)](https://github.com/mattxwang/easy-jekyll-starter/actions/workflows/gh-deploy.yml) [![Test Jekyll Build](https://github.com/mattxwang/easy-jekyll-starter/actions/workflows/test.yml/badge.svg)](https://github.com/mattxwang/easy-jekyll-starter/actions/workflows/test.yml)

Hey there! This is a simple template repository for [Jekyll](https://jekyllrb.com). It does two simple things over `jekyll new ...`:

* by default, ejects [minima](https://github.com/jekyll/minima) from its gem wrapper; this makes it easier to see what Jekyll is doing under the hood, and makes it easy to build your own theme
* adds two workflows for GitHub Actions:
  1. a test action that builds the site on PR/push
  2. an action to deploy to [GitHub Pages](https://pages.github.com/) off of `main`. Thanks to [`helaili/jekyll-action`](https://github.com/helaili/jekyll-action), this works out of the box with no secrets required

Other than that, I basically leave minima untouched.

For more information, [read this post](https://mattxwang.github.io/easy-jekyll-starter/jekyll/update/2019/09/05/easy-jekyll-starter.html)!

## Development Setup

Quick setup:

```sh
$ bundle
$ rake serve
bundle exec jekyll serve
Configuration file: /Users/malsf21/code/easy-jekyll-starter/_config.yml
            Source: /Users/malsf21/code/easy-jekyll-starter
       Destination: /Users/malsf21/code/easy-jekyll-starter/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
       Jekyll Feed: Generating feed for posts
                    done in 0.561 seconds.
 Auto-regeneration: enabled for '/Users/malsf21/code/easy-jekyll-starter'
    Server address: http://127.0.0.1:4000/easy-jekyll-starter/
  Server running... press ctrl-c to stop.
```

Or,

```sh
$ rake build
```

For more information, see [this post](https://mattxwang.github.io/easy-jekyll-starter/jekyll/update/2019/09/05/easy-jekyll-starter.html)!

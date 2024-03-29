---
layout: post
title:  "Easy Jekyll Starter - What and Why?"
author: matt
date:   2019-09-05 16:00:00 -0700
categories: jekyll update
---

Hey, thanks for using this starter template! I guess I should explain why this exists and what it does.

This is a simple template repository for [Jekyll](https://jekyllrb.com). It does two simple things over `jekyll new ...`:

* by default, ejects [minima](https://github.com/jekyll/minima) from its gem wrapper; this makes it easier to see what Jekyll is doing under the hood, and makes it easy to build your own theme
* adds two workflows for GitHub Actions:
  1. a test action that builds the site on PR/push
  2. an action to deploy to [GitHub Pages](https://pages.github.com/) off of `main`. Thanks to [`helaili/jekyll-action`](https://github.com/helaili/jekyll-action), this works out of the box with no secrets required

Other than that, I basically leave minima untouched.

Why did I make this simple template? I love using Jekyll, but I'm not a huge fan of how minima is now bundled by default into `jekyll new ...`. Firstly, it obscures some of the logic of what Jekyll is doing (via the minima gem), which makes it harder to introduce Jekyll to my friends. Since this template ejects minima out of its gem, it should be easier to understand how `_includes`, `_layouts`, and YAML front matter work!

In addition, it becomes a bit of a pain if you want to override some, but not all, of minima's defaults. Putting the SASS in `_sass` makes it easier to accomplish these kinds of changes.

Finally, I have a few preferences on how I usually run my Jekyll setups: I like using html-proofer to catch egregiously bad HTML (and check for dead links, though it's a bit inconsistent on that); I like aliasing the longer `bundle exec ...` commands to shorter keywords (like `rake build`); and, I Like using GitHub Actions to let me know if I've committed a bad build of the site.

Currently, this template uses Jekyll v4.0.0+.

## Development Setup

Admittedly, this is a little more annoying to use than `jekyll new ...`, but only slightly so.

To use this template, you'll need to have some sort of Ruby on your system; I recommend that you use [rvm](https://rvm.io/), especially if you work on multiple different Ruby projects. Currently, the Actions build uses Ruby `v2.7.4` and `v3.0.2` for test, and Ruby `3.0` for prod.

If you haven't already, we're first going to install [bundler](https://bundler.io/):

```sh
$ gem install bundler
```

Then, we'll install all of our dependencies from our `Gemfile`.

```sh
$ bundle
```

I've committed `Gemfile.lock`, which specifies what versions of gems to use. If you'd like, you can run `bundle update` to update them.

Now, you're ready to use the site! You can use `bundle exec jekyll serve` to serve the site, or `bundle exec jekyll build` to build it.

```sh
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

Those commands are a bit of a mouthful, so I've made quick rake shortcuts that will save you a few valuable keystrokes:

```sh
$ rake
# same as running bundle exec jekyll build
$ rake build
# also same as running bundle exec jekyll build
$ rake serve
# same as running bundle exec jekyll serve
```

In addition, I've also added html-proofer, which can test the validity of your HTML. You can use it like so:

```sh
$ rake build
...
$ rake test
Running ["ScriptCheck", "ImageCheck", "LinkCheck"] on ["./_site"] on *.html...
```

## Actions and GitHub Pages

Deploying off of GitHub Pages is very simple. We consume [`helaili/jekyll-action`](https://github.com/helaili/jekyll-action), which automatically builds and deploys the site. We don't need to pass in a specific environment token, as it uses the default `GITHUB_TOKEN` env var.

## A bit of history

This template used to use [Travis CI](https://travis-ci.com/), but for numerous reasons, I've decided to switch to GitHub Actions. One huge benefit is that you won't have to create a new access token!

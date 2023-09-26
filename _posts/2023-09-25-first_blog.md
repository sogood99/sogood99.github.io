---
title: Setup Jekyll with GitHub Pages
date: 2023-09-25 10:00:00 -0400
categories: [Programming, Configuration]
tags: [blogging, jekyll, github] # TAG names should always be lowercase
---

As my first blog post, I feel like I should describe how I deployed this blog. Basically, I used Jekyll to create a static website and deployed it to GitHub Pages.

## Jekyll

Jekyll is a simple, blog-aware static site generator that takes text written in Markdown, Liquid, HTML, or other formats and generates a static website ready to be hosted on a web server. It is the engine behind GitHub Pages and is widely used by developers for creating blogs, personal websites, and project documentation.

Initially, I wanted to use something like React, however, that seemed way too overkill for the relatively simple demand that I had, compared to Jekyll to write blogs is super easy.

## Prerequisites

Before we dive into the deployment process, make sure you have the following prerequisites in place:

### 1. GitHub Account

Log in to your GitHub account and create a new repository with name `yourusername.github.io`

### 2. Install RubyGems

Install RubyGems on your local computer, for Ubuntu, use APT to install:

```bash
sudo apt install ruby-rubygems
```

### 3.1 Create New Jekyll Project

If you want to create a fresh new Jekyll project, first install jekyll:

```bash
gem install bundler jekyll
```

Then create a new jekyll project

```bash
jekyll new my-website
```

configure the `_config.yml` file and add dependencies to `Gemfile` as you see fit. Then test it locally using:

```bash
bundle exec jekyll serve
```

### 3.2 Use Jekyll Template

For me, I basically used a Jekyll template online, namely the [Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy) template.

1. Fork the repo, then rename the repo to `yourusername.github.io`.
2. Usually the template has Author Name, Project URL, etc. configured in places like `_config.yml` and `_data/`.
3. Consider changing the favicon.

### 4. Deploy to GitHub

If your project doesn't have a pages-deploy under `.github` file, you can manually configure the repo to build and deploy.

1. Commit your code to the GitHub repo, then visit your GitHub repository's Settings page.

2. Go to the "GitHub Pages" section. Under "Source," select "main branch" and click "Save."

![Desktop View](/assets/img/2023-09-25-first_blog/github_pages.png){: width="700" height="400" }

3. You should see a GitHub action in tab "Actions", after it finished deploying, the page shoulde be live at `https://yourusername.github.io/`.

## NixOS Setup Attempt

Despite using `bundle` and `bundix`, I still wasn't able to get Chirpy to run on NixOS. It seems to have something to do with dependency `http_parser.rb` and the fact that it cannot generate . in `gemset.nix`.
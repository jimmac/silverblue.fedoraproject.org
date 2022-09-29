# Fedora Silverblue Website

This is the source of the silverblue website. Content written in markdown. 

## Setup

The process of setting up the site locally consists of:

- Install ruby [gem bundler](https://bundler.io/). On [Fedora](https://getfedora.org/)/in the [Toolbx](https://containertoolbx.org) you do:

```
toolbox enter
sudo dnf install rubygem-bundler
cd os-component-website
bundle install
```

Test the site locally:
```
bundle exec jekyll s
```

- `git commit` your changes and push to your remote repo for automatic deployment. There is an included `.gitlab-ci.yml` that should be easy to adjust to your gitlab hosting situation. For github pages situation, [see these instructions](https://pages.github.com/). 

Alternatively you can be wild and edit the site directly on github using the remote VSCode editor by pressing `.` after cloning the repo. Right in the browser. It's insane.

Written with love using [Apostrophe](https://flathub.org/apps/details/org.gnome.gitlab.somas.Apostrophe).

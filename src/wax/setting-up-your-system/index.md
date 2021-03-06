---
layout: default
title: Setting up your system
nav_order: 1
has_children: true
parent: Wax
permalink: /wax/setting-up-your-system/
---

# {{ page.title }}
{: .no_toc }

Since Wax produces static sites, all of the software runs on **your own computer**. This process spits out an HTML website that can be hosted easily without complex software on a server. This workflow is very freeing in terms of maintenance, but does mean there's a higher barrier to getting started initially.

We have a few installation guides and options available to help you through this process.


## Table of Contents
{: .no_toc }

1. TOC
{:toc}

## Requirements

Ultimately, you'll need:
- [x] [Ruby](https://www.ruby-lang.org/en/) (`>=2.4`) with [Bundler](https://bundler.io/)
- [x] [Git](https://git-scm.com/)
- [x] [ImageMagick](https://imagemagick.org/index.php)
- [x] [GhostScript](https://www.ghostscript.com/)
- [x] [Libvips](https://libvips.github.io/libvips/)\*


#### \***NOTE:** If you're using a newer `wax_tasks`, we also recommend you install __Libvips__, which will replace __ImageMagick__ in our stack.
{: .no_toc }

<br>
You can check your versions by running [the commands below](#check-for-requirements) in your terminal/shell of choice.

If you don't have current versions for these packages or are starting from scratch, see our [Installation Guides](#guides).

## Guides

You have two main options for installing the software needed for Wax: __manually on your machine__ or in a __Docker container__. Both options have pros and cons.

Both options \*should\* work across Mac, Windows, and Linux machines, so you should choose the option that makes the most sense for you and your use case.

### [Option 1: Install manually](install-manually/)

If you go this route:
- You'll install things one-by-one directly on your computer.
- The process will be more tedious, but you'll finish with a robust set of development tools that may be broadly applicable to other projects.
- Your software will run faster than it would in a Docker container.

### [Option 2: Install with Docker](with-docker/)

If you go this route:
- You'll install packages quickly within [Docker](https://www.docker.com/) "containers." This means the container will have just about everything you need in fewer steps.
- When you're not working on your Wax site, you can destroy the container (and all the software with it!), freeing up space on your computer.
- The downsides are that you'll need to start a container whenever you want to work with Wax, and the software will run a little slower than if you were running things on your host machine.

## Check for requirements

### Manual install checks

If you installed the software manually, you can run the following commands directly in your Terminal/shell app.

Check for Ruby:

```sh
ruby -v
```
#### \***NOTE:** This should be `>=2.4` and < `3.0`!
{: .no_toc }


Install & check for Bundler:

```sh
gem install bundler
bundler -v
```

Check for Git:

```sh
git --version
```

To process images, you will also need to have __ImageMagick__ and __Ghostscript__ installed and functional. (__Vips__ for later versions.)

Check ImageMagick:

```sh
convert -version
```

Check Ghostscript:

```sh
gs -version
```

Check Libvips:

```sh
vips -version
```

### Docker install checks

If you installed with Docker, all of the required software will be *inside* your Docker container **except for Git**, which is installed on your directly on your computer.

At this stage, you'll only need to check for Docker and Git by running the following checks in your Terminal/shell app.

Check Docker:
```sh
docker -v
```

Check Git:
```sh
git --version
```

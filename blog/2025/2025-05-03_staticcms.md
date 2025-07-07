<!-- Title: CMSless CMS -->
<!-- Date: 03/05/2025 -->
<!-- Keywords: static,github pages, cms, headless, content -->
<!-- Type: ARTICLE -->

# Creating a CMS-less CMS via publically hosted git repositories
The poor mans content-managed website...

The drive for a near-zero cost content-managed portfolio drove my exploration into seeing just how far I can take this experimental site.
I do this because I am cheap, not becasue I am smart.
The site itself is a content-sparse Vue SPA that, given a content URL, will crawl special files that define a directory structure and add them to a navigation tree as well as site config files for modules and services that run the site.

The site then uses this navigation tree to find the relevant content when a user tries to navigate to a page via URL or navigation and load the content on the page via a custom Markdown -> HTML -> VNode Parser that supports shortcodes.

This site is hosted on Github using Github pages. Except the content is hosted in another Github repo serving as a content repo that this current site can pull on.
This is an experiment,  not a recommendation. It's a “can I?” project, not a “should I?” one. It exists because I’m cheap, not clever. Expect breakage.

## Overview
This system relies on two dynamic sources.
* Configuration
* Content

Configurations are global site settings and can define the site's title content, footer content and how the navigation should behave.
Content is the pages and directories themselves, hosting the content that will become clickable and navigable on the site.
Both of these sources are found in the content repository.

The site utilises two main dynamic features, Configuration and Content. Both of which can live in the remote content repository.

## Configuration
Site configuration is a flat key-value map, managed in global state via a Pinia store. Keys follow a dot-delimited format like:
```
site.title=kaelyx
footer.copyright.name=kaelyx
footer.copyright.year=2025
```
Configuration of the site is handled by a single layered key-value map and held in global state with a pinia store.
Naming is for readability and logical grouping but does not get enforced.
### Load Order
1. Default Config
2. Remote Config
3. Local Dev Config (for development use)

Each Layer down can overwrite the previous value stored against a key.

## Content

### Fetching Content
Content is fetched from GitHub using the “Raw User Content” URL format, which serves plain text files from any given path, branch, or repo.

### Simulatoing Directory Navigations
GitHub’s raw content service doesn’t allow listing directories. To work around this, each folder includes a directory file that lists its contents. Example:
```
/folder_name
filename.md
```
* Entries with a leading `/` are subdirectories (expected to contain their own `directory` file.
* Entries without a `/` are files in the current directory.

#### Meta Names
The issue arises that a directory or file might not be named what you want it to be.
Meta names will appear in the nvaigation instead of the filename.
To customize how files or folders are displayed, append a colon and a label:
```
/folder_name: Blog
filename.md: My First day at the zoo
```

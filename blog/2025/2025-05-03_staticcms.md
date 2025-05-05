# Creating a Static CMS

This site is hosted on Github using Github pages. Except the content is hosted in another Github repo.
This site utilises Several modules and services to build a site based of the structure of a content repo.

This exploration into the feasability of this project is less of a "should I" and more of a "can I". Do as I say and not as I do. This site is experimental at best and a waiting TOS strike otherwise.

I do this because I am cheap, not because I am smart.

The site utilises two main dynamic features, Configuration and Content. Both of which can live in the remote content repository.

If you're interested, head over to the projects tab and find this project in there!

## Configuration

Configuration of the site is handled by a single layered key-value map and held in global state with a pinia store.
the keys can take on any shape but to keep simplicity and a paradigm for finding or modifying a key, a "." (dot) delimited string outlining "area.feature.key" such as "footer.copyright.name" or "site.title". These are not enforced but keep it easier to read and group certain values together.

### Precedence

The configuration is loaded in a certain order to ensure values are available for the site to use as sensible defaults.

1. Loads the default config
2. Loads remote config values
3. Loads the dev / override config values (Mostly for development)

Each config can override a previous configuration value.

## Content

### Getting Content

Getting content is simple, it uses Gitihubs "Raw user content" Service which, provided a path to a branch, folder and file will output that file as plain text.

### Navigatable directories without being able to see directories

The downside of Githubs "raw user content" service is that it cannot provide a method for navigating file or directories within a branch or repository. To counteract this, a special file is places in every directory, the "directory" file. this file has a known name and no extenstion which tells the site what is in this directory.

The structure of the directory file might look like:

```
/folder_name
filename.md
```

The leading slash denotes that this is a directory and will have a directory file located within it which the directory walker, we will get on to that, can use to navigate further.
files are denoted with no leading slash but also are not required to have a dot denoted filetype at the end.

This means when we see a `/folder_name` , we know a file named `directory` will exist in that folder that we can read to understand the contents of that folder.

#### Meta Names

The issue arises that a directory or file might not be named what you want it to be, meta names are defined by a semi-colon after the file or directory and then a string. this string will be used in place of the name of the file or directory when rendered on the site.

```
/folder_name: Blog
filename.md: My First day at the zoo
```

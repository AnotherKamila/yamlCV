yamlCV
======

An awesome YAML-based CV that works with your existing Jekyll site

Example: [kamila.is/awesome](https://kamila.is/awesome) :-)

What this is
------------

Takes YAML as input (such as [this](https://github.com/AnotherKamila/kamila.is/blob/master/_data/cv.yml)) and produces pretty HTML (such as [this](https://kamila.is/awesome)) using Jekyll. Works also with GitHub Pages.

**Why:** The YAML input is maintainable and easy to change, so updating my CV is no longer annoying.
And Jekyll integration makes my pretty data also look pretty on my pretty website, automatically.

How to use
----------

First, **tell Jekyll your data**. The simplest way is to add a `_data/cv.yml` file. The syntax is hopefully obvious from [this example](./example-data.yml).

Then, **stuff `cv.html` into Jekyll**. There are multiple ways to achieve that, the simplest being just copying `cv.html` into `something.html` (and adding a front matter).

A method easier to maintain is to add this repository as a Git submodule, symlink `cv.html` into `_includes/`, and then `{% include cv.html %}` in pages. You can see this setup [on my website](https://github.com/AnotherKamila/kamila.is/blob/master/cv/index.html). How to:

```sh
cd <your-site>/_includes  # you need to put it under _includes because jekyll doesn't like arbitrary symlinks
git submodule add https://github.com/AnotherKamila/yamlCV.git
ln -s yamlCV/cv.html .
```

Customization
-------------

### Colors

The template expects the following CSS classes to exist:

- `text-primary { color: your-primary-color; }`: used for the section titles and link color
- `text-muted { color: some-grey; }`: used for the "tagline"

If you use Bootstrap, these should be already present.

### Settings

You can add the following into the page's front matter:

```yaml
cv:  # all CV settings go under this
    download_links:
        PDF: url.pdf
        YAML: url.yml
        Whatever: anything you put here will show up as a download link in the upper right corner
    no_lines: true  # set this if you don't like the horizontal lines that go with section titles
```

Pull requests are welcome!
--------------------------

As always ;-)

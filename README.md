# Github Organization Guidelines (Mkdocs build)

> This documentation outlines the rules, conventions, and best practices for using this GitHub organization to share and collaborate on scientific resources. It serves as a guide to ensure consistent and effective source management across our team

The documentation is available at : LINK HERE

## Overview

The pages are written in Markdown format.

All pages are strored in folder `docs/` and written in Markdwon format.

All related figures are stored in folder `docs/assets/` and saved as PNG.

The documentation is built as a static HTML web site with Mkdocs (https://www.mkdocs.org/getting-started/)

The rendering is configured with a config file at the root folder named `mkdocs.yml`.

## Installation 

Installing mkdocs :

```
python -m pip install mkdocs
```

Installing mkdocs third-party themes

```
python -m pip install mkdocs-material
```

Other themes 

```
mkdocs-nature mkdocs-github mkdocs-gitbook mkdocs-custommill mkdocs-windmill mkdocs-theme-bootstrap4 mkdocs-ivory mkdocs-swan mkdocs-alabaster
```

Best theme for scientific documentation are `material`, 
 `readthedocs`, `swan`, or `alabaster`


## Live HTML pages

```
python -m mkdocs serve
```

Open the this link in browser : http://127.0.0.1:8000/


## Build site before deployment

```
python -m mkdocs build
```

The site ready-to-deploy is created in the `site/` folder.

Add this to to .yml file to generate local HTML documentation with proper links.

```
site_url: ""
use_directory_urls: false
plugins: []
```

## Modify the page menu

To change the way pages are shown in the site web, modify the `nav` section of the configuration file `mkdocs.yml` (see [Mkdocs documentation](https://www.mkdocs.org/user-guide/configuration/#documentation-layout))

## Rendering LaTex equations

To render LaTex equation embeded in your markdown document with `$ ... $` (inline equation) or with `$$ ... $$` (equation blocks) follow instruction on the [Mkdocs documentation](https://squidfunk.github.io/mkdocs-material/reference/math/#mathjax-mkdocsyml)  

Step 1 : Add this to the .yml configuration file

```
markdown_extensions:
  - pymdownx.arithmatex:
      generic: true
extra_javascript:
  - javascripts/mathjax.js
  - https://unpkg.com/mathjax@3/es5/tex-mml-chtml.js
```

Step 2 : And Create a new file `mathjax.js` in folder `docs/javascripts/` with the following content

```
window.MathJax = {
    tex: {
      inlineMath: [['$', '$'], ['\\(', '\\)']],
      displayMath: [['$$', '$$'], ['\\[', '\\]']],
      processEscapes: true,
      processEnvironments: true
    },
    options: {
      ignoreHtmlClass: ".*|",
      processHtmlClass: "arithmatex"
    }
  };
  
  document$.subscribe(() => { 
    MathJax.startup.output.clearCache()
    MathJax.typesetClear()
    MathJax.texReset()
    MathJax.typesetPromise()
  })
```

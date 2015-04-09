---
layout: post
title:  "Introducing Radiant: A shiny interface for R"
categories: [rstats]
tags: [rstats, Shiny]
---

Radiant is a platform-independent browser-based interface for business analytics in [R](http://www.r-project.org/), based on the [Shiny](http://www.rstudio.com/shiny/) package.

## Key features

- Explore: Quickly and easily summarize, visualize, and analyze your data
- Cross-platform: It runs in a browser on Windows, Mac, and Linux
- Reproducible: Recreate results at any time and share work with others as a state file or an [Rmarkdown](http://rmarkdown.rstudio.com/) report
- Programming: Integrate Radiant's analysis functions into your own R-code
- Context: Data and examples focus on business applications

<iframe width="640" height="375" src="https://www.youtube.com/embed/ioHopyfD2f0" frameborder="0" allowfullscreen></iframe>

#### Explore

Radiant is interactive. Results update immediately when inputs are changed (i.e., no separate dialog boxes). This greatly facilitates exploration and understanding of the data.

#### Cross-platform

Radiant works on Windows, Mac, or Linux. It can run without an Internet connection and no data will leave your computer. You can also run the app as a web application on a server.

#### Reproducible

Simply saving output is not enough. You need the ability to recreate results for the same data and/or when new data become available. Moreover, others may want to review your analysis and results. Save and load the state of the application to continue your work at a later time or on another omputer. Share state files with others and create reproducible reports using [Rmarkdown](http://rmarkdown.rstudio.com/).

If you are using Radiant on a server you can even share the url (include the SSUID) with others so they can see what you are working on. Thanks for this feature go to [Joe Cheng](https://github.com/jcheng5).

#### Programming

Although Radiant's web-interface can handle quite a few data and analysis tasks, at times you may prefer to write your own code. Radiant provides a bridge to programming in R(studio) by exporting the functions used for analysis. For more information about programming with Radiant see the [programming](http://vnijs.github.io/radiant/programming.html) page on the documentation site.

#### Context

Radiant focuses on business data and decisions. It offers context-relevant tools, examples, and documentation to reduce the business analytics learning curve.

## How to install Radiant

- Required: [R](http://cran.rstudio.com/) version 3.1.2 or later
- Required: A modern browser (e.g., [Chrome](https://www.google.com/intl/en/chrome/browser/desktop/) or Safari). Internet Explorer (version 11 or higher) should work as well
- Recommended: [Rstudio](http://www.rstudio.com/products/rstudio/download/)

Radiant is available on [CRAN](http://cran.r-project.org/web/packages/radiant/index.html). To install the latest version with complete documentation for offline access open R(studio) and copy-and-paste the command below:

```
install.packages("radiant", repos = "http://vnijs.github.io/radiant_miniCRAN/")
```

Once all packages are installed use the commands below to launch the app:

```
library(radiant)
radiant("marketing")
```

See also the `Installing Radiant` video:

<iframe width="640" height="375" src="https://www.youtube.com/embed/NEPSFiHH_dw" frameborder="0" allowfullscreen></iframe>

## Documentation

Documentation and tutorials are available at <http://vnijs.github.io/radiant/> and in the Radiant web interface (the `?` icons and the `Help` menu).

Want some help getting started? Watch the tutorials on the [documentation site](http://vnijs.github.io/radiant/tutorials.html)

## Online

Not ready to install Radiant on your computer? Try it out online at <http://vnijs.rady.ucsd.edu:3838/marketing>. Note that this is a test server only!

Please send questions and comments to: radiant@rady.ucsd.edu.

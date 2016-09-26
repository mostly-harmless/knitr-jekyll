---
layout: post
title:  "Re-introducing Radiant: A shiny interface for R"
categories: [rstats]
tags: [rstats, Shiny]
---

Radiant is a platform-independent browser-based interface for business analytics in [R](http://www.r-project.org/). I first introduced Radiant through R-bloggers on 5/2/2015 and, according to, Dean Attali the post was [reasonably popular](http://deanattali.com/2015/05/17/analyzing-rbloggers-posts-via-twitter/). So I decided to write a post about the changes to the tool since then.

Radiant is back on [CRAN](https://cran.r-project.org/web/packages/radiant/index.html) and the code and documentation have been moved to a GitHub organization [radiant-rstats](https://github.com/radiant-rstats). Note that the app is only available for R 3.3.0 or later.

There have been numerous changes to the functionality and structure of Radiant. The app is now made up of 5 different menus, each in a separate package. The **Data** menu (`radiant.data`) includes interfaces for loading, saving, viewing, visualizing, summarizing, transforming, and combining data. It also contains functionality to generate reproducible reports of the analyses conducted in the application. The **Design** menu (`radiant.design`) includes interfaces for design of experiments, sampling, and sample size calculation. The **Basics** menu (`radiant.basics`) includes interfaces for probability calculation, central limit theorem simulation, comparing means and proportions, goodness-of-fit testing, cross-tabs, and correlation. The **Model** menu (`radiant.model`) includes interfaces for linear and logistic regression, Neural Networks, model evaluation, decision analysis, and simulation. The **Multivariate** menu (`radiant.multivariate`) includes interfaces for perceptual  mapping, factor analysis, cluster analysis, and conjoint analysis. Finally, the `radiant` package combines the functionality from each of these 5 packages.

More functionality is in the works. For example, naive Bayes, boosted decision trees, random forests, and choice models will be added to the **Model** menu (`radiant.model`). I'm also planning to add a **Text** menu (`radiant.text`) to provide functionality to view, process, and analyze text.

If you are interested in contributing to, or extending, Radiant, take a look at the code for the [`radiant.design`](https://github.com/radiant-rstats/radiant.design) package on GitHub. This the simplest menu and should give you a good idea of how you can build on the functionality in the `radiant.data` package that is the basis for all other packages and menus.

Want to know more about Radiant? Although you could take look at the original [_Introducing Radiant_](http://vnijs.github.io/blog/2015/05/introducing-radiant.html) blog post, quite a few of the links and references have changed. So to make things a bit easier, I'm including an updated version of the original post below.

If you have questions or comments please email me at radiant@rady.ucsd.edu

## Key features

- Explore: Quickly and easily summarize, visualize, and analyze your data
- Cross-platform: It runs in a browser on Windows, Mac, and Linux
- Reproducible: Recreate results at any time and share work with others as a state file or an [Rmarkdown](http://rmarkdown.rstudio.com/) report
- Programming: Integrate Radiant's analysis functions into your own R-code
- Context: Data and examples focus on business applications

<iframe width="640" height="375" src="https://www.youtube.com/embed/7L3hDpLw53I" frameborder="0" allowfullscreen></iframe>

#### Explore

Radiant is interactive. Results update immediately when inputs are changed (i.e., no separate dialog boxes). This greatly facilitates exploration and understanding of the data.

#### Cross-platform

Radiant works on Windows, Mac, or Linux. It can run without an Internet connection and no data will leave your computer. You can also run the app as a web application on a server.

#### Reproducible

Simply saving output is not enough. You need the ability to recreate results for the same data and/or when new data becomes available. Moreover, others may want to review your analyses and results. Save and load the state of the application to continue your work at a later time or on another computer. Share state files with others and create reproducible reports using [Rmarkdown](http://rmarkdown.rstudio.com/).

If you are using Radiant on a server you can even share the url (include the SSUID) with others so they can see what you are working on. Thanks for this feature go to [Joe Cheng](https://github.com/jcheng5).

#### Programming

Although Radiant's web-interface can handle quite a few data and analysis tasks, you may prefer to write your own code. Radiant provides a bridge to programming in R(studio) by exporting the functions used for analysis. For more information about programming with Radiant see the [programming](http://radiant-rstats.github.io/docs/programming.html) page on the documentation site.

#### Context

Radiant focuses on business data and decisions. It offers context-relevant tools, examples, and documentation to reduce the business analytics learning curve.

## How to install Radiant

- Required: [R](http://cran.rstudio.com/) version 3.3.0 or later
- Required: A modern browser (e.g., [Chrome](https://www.google.com/intl/en/chrome/browser/desktop/) or Safari). Internet Explorer (version 11 or higher) or Edge should work as well
- Recommended: [Rstudio](http://www.rstudio.com/products/rstudio/download/)

Radiant is available on [CRAN](http://cran.r-project.org/web/packages/radiant/index.html). However, to install the latest version of the different packages with complete documentation for offline access open R(studio) and copy-and-paste the command below into the console:

```r
install.packages("radiant", repos = "http://radiant-rstats.github.io/minicran/")
```

Once all packages and dependencies are installed use the following command to launch the app in your default browser:

```r
radiant::radiant()
```

If you have a recent version of Rstudio installed you can also start the app from the `Addins` dropdown. That dropdown will also provide an option to upgrade Radiant to the latest version available on the github minicran repo.

If you currently only have R on your computer and want to make sure you have all supporting software installed as well (e.g., Rstudio, MikTex, etc.) open R, copy-and-paste the command below, and follow along as different dialogs are opened:

```r
source("https://raw.githubusercontent.com/radiant-rstats/minicran/gh-pages/install.R")
```

More detailed instructions are available on the [install radiant](attps://radiant-rstats.github.io/docs/install.html) page.

## Documentation

Documentation and tutorials are available at http://radiant-rstats.github.io/docs/ and in the Radiant web interface (the `?` icons and the `Help` menu).

Want some help getting started? Watch the tutorials on the [documentation site](http://radiant-rstats.github.io/docs/tutorials.html)

## Radiant on a server

If you have access to a server you can use shiny-server to run radiant. First, start R on the server with `sudo R` and install radiant using `install.packages("radiant")`. Then clone the [radiant repo](https://github.com/radiant-rstats/radiant) and point shiny-server to the inst/app/ directory.

If you have Rstudio server running and the Radiant package is installed, you can start Radiant from the addins menu as well. To deploy Radiant using Docker take a look the example and documentation at:

<a href="https://github.com/radiant-rstats/docker-radiant" target="_blank">https://github.com/radiant-rstats/docker-radiant</a>

Not ready to install Radiant, either locally or on a server? Try it out on shinyapps.io at the link below:

<a href="https://vnijs.shinyapps.io/radiant" target="_blank">vnijs.shinyapps.io/radiant</a>

Send questions and comments to: radiant@rady.ucsd.edu.

-------------------
aggregated on [R-bloggers](http://r-bloggers.com/) - the complete collection of blogs about R

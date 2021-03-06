<!--
%\VignetteEngine{knitr::knitr}
%\VignetteIndexEntry{Getting started with Roxygen2}
-->



# Introduction to roxygen2

Documentation is one of the most important aspects of good code. Without it, users won't know how to use your package, and are unlikely to do so. Documentation is also useful for you in the future (so you remember what the heck you were thinking!), and for other developers working on your package. The goal of roxygen2 is to make documenting your code as easy as possible. R provides a standard way of documenting packages: you write `.Rd` files in the `man/` directory. These files use a custom syntax, loosely based on latex. Roxygen2 provides a number of advantages over writing `.Rd` files by hand:

* Code and documentation are adjacent so when you modify your code, it's easy
  to remember that you need to update the documentation.

* Roxygen2 dynamically inspects the objects that it's documenting, so it
  can automatically add data that you'd otherwise have to write by hand.

* It abstracts over the differences in documenting S3 and S4 methods,
  generics and classes so you need to learn fewer details.

As well as generating `.Rd` files, roxygen will also create a `NAMESPACE` for you, and will manage the `Collate` field in `DESCRIPTION`.

This vignette provides a high-level description of roxygen2 and how the three main components work. The other vignettes provide more detail on the individual components:

* [Generating .Rd files](rd.html) and [text formatting](formatting.html)
  describe how to generate function documentation via `.Rd` files

* [Managing your `NAMESPACE`](namespace.html) describes how to generate
  a `NAMESPACE` file, how namespacing works in R, and how you can use Roxygen2 to be
  specific about what your package needs and supplies.

* [Controlling collation order](collate.html) describes how roxygen2
  controls file loading order if you need to make sure one file is
  loaded before another.

# Running roxygen

There are three main ways to run roxygen:

* `roxygen2::roxygenise()`, or

* `devtools::document()`, if you're using devtools, or

* `Ctrl + Shift + D`, if you're using RStudio.

As of version 4.0.0, roxygen2 will never overwrite a file it didn't create. It does this by labelling every file it creates with a comment: "Generated by roxygen2 (version): do not edit by hand".

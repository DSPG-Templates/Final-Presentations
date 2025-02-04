# Project Final Blogs
Harun Celik
2024-07-19

# Goal of the Final Presentation

Unlike the weekly blogs, the final presentation is the culmination of
all the work completed throughout the full summer program for DSPG. This
means that the final blog will be;

- Longer and should cover the material from the inception of the
  project.
- Explanatory of project concepts relevant to a general audience.

Even if your headers are slightly different, try to structure the
presentations so that they at least contain the following sections.

    Introduction
      Introduce the Members
      Introduce the Project
        Research Question/Goal
          What is the Project Trying to Achieve (and Why?)
          What were the Goals for this Project?
        Structure of the Presentation

    Data Sources
      Data Availability
      Searching for Data
      Collecting Data

    Data Processing
      How was it Processed
      What Tools were Used (and Why?)
      How did it look? How does it look now?

    Demonstration of Project
      Discussion of Challenges
        What were the Most Challenging Components of the Project?
        Were they Overcome? (and How?)
        What Challenges Remain?

    Conclusion
      Reinstate the Project Goals
        Did the Project Meet/is Meeting the Goals?
      Future Work

## Previous Examples

The following are blog presentations from the previous year (2023). Use
them as a reference for the structure of the presentations since your
contents will be different. *They are not examples of best practices,
only how the blogs were structured before*

Using Data to Inform Decision Making for Rural Grocery Stores  
You can find blog post by following this
[link](https://averagedocudramaenjoyer.github.io/Aaron-N-s-Blog/posts/Final_Presentation_Grocery/Final_Presentation_Grocery.html#conclusion)
and the markdown used to generate the page following this
[link](https://github.com/DSPG-2023/DSPG2023/blob/main/blog2023/FinalPresentation/Grocery-Final-Presentation/Grocery_Final_Presentation.qmd).

Housing Project  
You can review the blog post by viewing this
[link](https://morenikeope.github.io/Atejioye_Blog/posts/Report_Draft/Report_Draft.html#ai-driven-housing-evaluation-for-rural-community-development)
and the markdown used to generate the page by following this
[link](https://github.com/DSPG-2023/DSPG2023/blob/main/blog2023/FinalPresentation/Housing-Final-Presentation/Housing_Final_Presentation.qmd).

## Important Considerations

The following are things to consider when making the final blogs.

- While the format is a blog, aim to present the material as visually as
  possible. It’s okay to have the text there so that people are able to
  come back to the material and read in further detail, but don’t expect
  people to read much during the presentation.
- Make sure that your visuals are placed, labelled, and sized correctly
  so that they are visible to the audience members as you are
  presenting.
- Demonstrations should be left to the end and there should be an
  already implemented backup option if they are not possible.
  - For example, if trying to demonstrate a dashboard have a short video
    or GIF already embedded into the blog. If time and technology
    permits, do a live demonstration. Otherwise let the audience view
    the video.

# Markdown Guidelines

Your final blog file should be `Final_Team_Blog.qmd` file. Don’t change
the name or the GitHub Actions check will fail.

## Metadata

- Adjust the author above so that the appropriate one of
  `["Housing and AI", "Community Capitals", "Iowa Zoning Guide"]` is
  selected.
- Change the title of the blog to `"$PROJECT Final Presentation"`,
  adjusting for each group. The categories are case sensitive.

## Images

Since this post doesn’t specify an explicit `image` in the YAML, the
first image in the post will be used as the thumbnail of the post. You
can add a specific image in the YAML. A couple of things to remember
with linking images.

- Place your images in the `imgs` directory. This helps prevent clutter
  and makes it easier to find the files.
- Name your images explicitly. Don’t call them `"image_1.jpg"` but
  instead something like `"age_scatterplot_1"`.
- Don’t save file names with any spaces. Add an `_` or use
  `camelCaseNaming`. Spaces will prevent the blog from properly
  rendering!
- Make sure you follow copyright guidelines on images. Don’t add images
  you would not be permitted to share in any professional environment.

## Data Guidelines

Here are some important things to consider when you’re using data sets
in your blogs.

- VERY IMPORTANT: All data saved in the `data` directory is publicly
  visible. Don’t share data that is private into your blogs.
- Be mindful of the size of your data. The larger the data, the longer
  it will take to render. GitHub also limits commit sizes so keep this
  in mind.
- Save your data as an `.RDS` file when possible to save space and to
  preserve the data types of columns.

## Adding Dependencies

In order for the blogs to render on other another device we need to
ensure that the packages used to render and run the code will also be
available for others using your project. R uses a `DESCRIPTION` file to
keep track of all package dependencies, you can use the `usethis`
library to keep track of packages.

For example, if we are using the `ggplot2` library, we would run the
following.

``` r
usethis::use_package(package = "ggplot2", type = "Imports")
```

You should now be able to see `ggplot2` as an import at the bottom of
the `DESCRIPTION` file.

    Package: Weekly Blogs
    Title: What the Package Does (One Line, Title Case)
    Version: 0.0.0.9000
    Authors@R: 
        person("First", "Last", , "first.last@example.com", role = c("aut", "cre"),
               comment = c(ORCID = "YOUR-ORCID-ID"))
    Description: What the package does (one paragraph).
    License: `use_mit_license()`, `use_gpl3_license()` or friends to pick a
        license
    Encoding: UTF-8
    Roxygen: list(markdown = TRUE)
    RoxygenNote: 7.0.0
    Imports: 
        ggplot2

- Make sure that all the packages you are using are added to
  `DESCRIPTIONS`.
  - One way to make sure is to Restart your session and try to run all
    of your code in order to see if any library is not called but loaded
    from another session.
- Don’t include the `tidyverse` in imports, use the specific libraries
  instead.

## Using Python Code Chunks

If you are using python in your code chunks you will need to run the
following at the top of your code, after the library imports. Set the
following chunks to `eval=TRUE`.

``` r
# Library for running python code in RStudio.
library(reticulate)
```

``` r
# Check for virtual environment, if it doesn't exist, create the venv, if it exists
# then use the venv called "r-python"

if (virtualenv_exists("r-python")) {
  use_virtualenv("r-python")
} else {
  virtualenv_create("r-python")
  use_virtualenv("r-python")
}
```

``` r
# Installing dependencies for the python virtualenv

virtualenv_install(envname = "r-python", packages = c("numpy", "pandas", "scikit-learn"), all = TRUE)
```

# Markdown Resources

- [Quarto Tutorials](https://quarto.org/docs/guide/)
- [Quarto Websites/Blogs](https://quarto.org/docs/websites/)
- [Quarto Markdown Reference
  Guide](https://quarto.org/docs/authoring/markdown-basics.html)
- [RMarkdown Reference
  Guide](https://www.rstudio.com/wp-content/uploads/2015/03/rmarkdown-reference.pdf)

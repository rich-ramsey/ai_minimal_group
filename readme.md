This project analyses data for the AI minimal group project.

# What is the easiest way to access this project? #

If you want to see and work with the code, then:

1. Clone, fork or download the project from github to your local machine.
See this link for the difference between cloning and forking. https://github.com/orgs/community/discussions/35849

2. Open the analysis.Rproj file and renv() will automatically bootstrap itself.

3. Use renv::restore() to install all of the packages. Say yes.

4. At this point, you can use the project with the same package versions that are stored in the renv.lock file.

# System requirements #

We performed data analysis in the R programming language (v4.4.0; R Core Team, 2024). 
All package dependencies were recorded and controlled via renv(). 
For an introduction to renv() for package management, see here: https://rstudio.github.io/renv/articles/renv.html.

# General structure of files and folders #

At the top level of the folder, there are several files.

- There is one R project file:

**analysis.Rproj**. 

- There are several R markdown files:

**wrangle.Rmd**

This is the primary data wrangling file, which reads in the raw data file and transforms it for further analysis. This files also creates descriptive statistics and plots. It writes out two data files that are subsequently used for further analysis. This file is intended to be used in successive chunks or executed in its entirety. Both options are fine. 

**model.Rmd**

This file builds a series of Bayesian regression models and performs some model checks and comparisons. This file is only intended to be used in successive chunks (and not with one click). The code would need modifying the run in its entirety. The models take seconds or minutes to run on standard desktop machines. Before you run the model script, you need to create a folder called **/models/** in the top level directory.

**effects_index.Rmd**

**effects_factorial.Rmd**

These effects files read in the full model, plots parameter estimates and calculates model fits. There are two separate files, one for the index coding models and one for the factorial model.

**renv.lock**

renv() produces a plain text file that records all package versions.

There are also folders, with self-explanatory titles: 

**/data/**

**/figures/**

**/tables/**

# How do I use the files? #

First, create a folder called **/models/** in the top level directory.

If you want reproduce the entire workflow, then start with the wrangle file, then the model file and then the effects files.

Alternatively, you could run the model scripts by reading in the pre-wrangled and saved data. 

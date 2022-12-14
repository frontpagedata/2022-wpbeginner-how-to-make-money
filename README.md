# SOP Data Analysis and Project Template

Last updated: 18.12.2020

## 1 Introduction

This document walks you through the process of analyzing data at [FrontPage Data](https://frontpagedata.com/)

**What we do at FrontPage Data:** Like a digital PR service, we aim to raise awareness about our customers in the online space. Our weapon of choice is outstanding content. 

**How we do it:** We help companies to generate interesting topics for content, analyze and visualize their data, then transform these insights into quality content marketing that spreads. Our content tells a story through data and explains what the findings mean to readers.

**What we're trying to achieve:** Our customers want to improve their online visibility with outstanding content. Effective content will generate links from notable sites, secure write ups in online publications, improve rankings on Google results, and generate buzz around the brand. 

**Why you should care:** An outstanding data report is integral to our business model and the success of our customers. Nobody wants to read or pay for lackluster content. Your aim is to create a client facing data-report that serves as the basis for a standout content piece.

**This is a very important task, so please read these guidelines closely.**

------------------------------------------------------------------------

## 2 Setup

In most instances, we provide a data set for you to analyze. We´ll provide context, share a project brief, prepare a short overview of the data by sending you a loom video, and discuss what type of research questions/cool angles might be worth exploring.

Once everything is clear on what needs to be done, we´ll get started with the analysis.

## R Project Analysis Template - Full (Master)

This template is meant to guide and structure your analysis projects in R. Delete the contents of this readme and fill it out again with your actual project readme. Guide for [markdown formatted text](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

The folder structure helps to organize data and scripts according to their purpose and facilitate easy reuse of project work flows on new data sets. Feel free to delete every portion that doesn't fit your needs.

## Project Setup with this Template and RStudio

1.  Create a project-specific repository in frontpagedata repo. Set to private. We add you as a project member.

2.  When creating the repo, select the template *project-template*

3.  Use Sourcetree or another git client manager to clone the repository. Copy github url link and clone. 

3.1 Create folder where you want the project to live on your computer.

5.  Load [RStudio](https://www.rstudio.com/) (are you not using RStudio? You really should be ;))

6.  Click *File\>New Project...\>Existing Directory*

7.  Select the unzipped template folder then *Create Project*

8.  If you already have some files like datasets and code, copy it over to your folder. 

9.  Commit changes to the project-specific repository.

Start working! ⌨️

------------------------------------------------------------------------

### File structure

    +-- plots                 <- folder for final and polished charts and maps
    +-- proc_data             <- Script outputs (eg. cleaned data) 
    +-- raw_data              <- Raw data goes here. Do not modify raw data in place. This isn't Excel.  
    \-- rmd                   <- R markdown documents
        +-- 01_read.Rmd       <- Set up script to read in raw data and do basic cleaning   
        +-- 02_analysis.Rmd   <- main analysis, advanced cleaning, data modeling and polishing charts 
        +-- 03_final.Rmd      <- final file with polished graphs and results description for client 
        +-- 04_convert_pdfs_to_pngs.Rmd <- plots that are in pdfs will be converted into the pngs using
    \-- scripts               <- scripts folder for everything else. 
        +-- render_upload.R   <- uploading final HTML file to website
    +-- doc                   <- intermediarie files (pdfs, docx)     
    +-- study_name.Rproj
    +-- README.md             <- This file. Replace it with an explanation of your project
    +--.gitgnore              <- Tells Git which files it shouldn't monitor. Please adjust. 

Note: `02_analysis.Rmd` and `03_final.Rmd` contain code snippets. See below for an explanation.

Note 2: More information in the respective `README.md` folder files.

------------------------------------------------------------------------

## 3 Data Analysis Process

At first, following through the specifications may seem a lot but it helps to keep things organized and at the same time reduces the amount of emails/phone calls. Once you got a hang of it, it should be easy to get started.

Let´s dive in! 🤿

#### `02_analysis.Rmd`

This is were the data analysis magic is going on. This file is for internal use only and will not be shown to the client. Data visualizations should be finalized in this file. For our data analysis, we follow the [KISS principle](https://www.interaction-design.org/literature/article/kiss-keep-it-simple-stupid-a-design-principle) - Keep it simple and stupid. That means that we want to start out our EDA as simple as possible and then, if needed, iteratively add more stuff (modeling, fancy visualizations etc). There have been too many times where we did nice visualizations without ever being used by the client. That´s wasted life time.

As mentioned above, before we get started, we discuss what research questions may make sense or would be cool to look at.

**Always keep our mission in mind: We help companies come up with interesting topics, analyze and visualize their data, and turn the insights into great content that spreads.**

We envision the process as follows:

1.  Start with a simple analysis and a few selected variables (see David Robison´s youtube channel for some inspiration: <https://www.youtube.com/channel/UCeiiqmVK07qhY-wvg3IZiZQ>.\
    You circle back to us. If looks good, keep going. If not, "looks cool but may make sense to look at x instead of y". Or we discuss further what might be worth exploring.

2.  Do some more advanced stuff (e.g. modeling) if needed and appropriate for the task at hand.

3.  Rinse and repeat

**Important note:** You may want to create nice looking data visualizations if they serve the purpose but please do not tweak details like coloring, wording, etc. yet. This should be done once the client approved the plots and the findings. KISS! 💋

Some technical notes:

-   Please feel free to split the analysis into various rmd files to keep the analysis organized. This may be in particular useful for longer analysis e.g `02_sec01_name.rmd` , `02_sec02_name.rmd` etc.

-   Every ggplot should be saved into pngs under the `plots/` folder. To do that, we want to generate first the pdfs that will be then generated into pngs. Code snippets are added for that purpose.

-   Please do not include ggplot in your functions. Yes, it´s less code but harder to polish and adjust if needed.

-   When doing the EDA, please provide some key summary stats for the variable of interest. This can be showcased with a summary function or custom coded table (see example in rmd file).

-   Plot titles: Please use some basic descriptive title to make your point. However, do not spend too much time on it. Our business writer will replaces those with his own.

-   Axis label: Please be consistent when naming your axis.

-   Basic theme and color code settings have been added. Please adjust according to the client´s brand profile. Should be polished and worked on at the end of the project. Again, KISS! 💋

-   Please provide meaningful commit messages.

-   We´ll send you a seperate .zip file with the data files if the size exceeds github´s 100mb limit. Please remind us to send you the files.

#### `03_final.Rmd`

This will be the client facing data report. We like to keep the analysis seperated from the main findings document/report.

Generally, we like to structure the final report loosely to academic papers. That way, interested readers can always fall back to the html output if they want to read more about the methodology or look up detailed findings. It also keeps the analysis organized. However, please feel free to apply below structure to your `02_analysis.rmd` so we can simply copy-paste your findings to the `03_final.Rmd` file. Whatever works best in your work flow.

Report Structure is usually as follows:

1.  Introduction (Daniel takes care of that most of the time)
2.  Methodology
3.  Research findings
4.  Annex (more info can be found in the rmd file) (optional)

Please **always** add written description of the findings. If the findings are more technical and need explanation, always provide some bulleted short key takeaways. Below for a simple building structure of a example:

**1. Research finding X**

*here description finding 1*

*here description finding n*

*here key summary stats of variable of interest*

*here plot 1*

*here plot n*

**2. Research finding Y**

**etc.**

Some notes:

-   Get to the point when describing the results. You may interpret results to add some context to the findings. But don´t add unnecessary fluff.

-   We use the `knitr::include_graphics` function to reference plots from the `plots/` folder. Code provided.

-   Please use a coherent title numbering e.g. 2.1 , 2.2., etc.

-   If you have some questions about a variable, unsure on how to proceed or something else that needs attention, just leave a comment like so in the rmd doc with your first initial e.g. `!!!D: I need your input here!`

#### Examples

See here for some data reports and the resulting final blog posts that were created for a client in the past:

1.  Data report: <https://frontpagedata.com/projects/backlinko/keyword-analytics/Final_Analysis.html>; Final blog post: <https://backlinko.com/keyword-research-tool-analysis>

2.  Data report: <https://frontpagedata.com/projects/backlinko/user-research/final.html>; Final blog post: <https://backlinko.com/google-user-behavior>

------------------------------------------------------------------------

## 4 Review process

You are expected to participate in the review process which may continue for several days after you've submitted the data report draft.

The rough process is as follows (which may vary depending on the client´s workflow):

1.  We sent off the draft data report (html file) to our client for comments.

2.  Depending on the client, the comments are either send by email or are provided in a Google Doc.

3.  If the comments have been cleared, we enter the write-up phase. Either our business writer or the client´s in-house prepares the report.

    1.  If our business writer is responsible, he/she prepares the outline first. If the outlines get´s the okay from the client, we finalize the report.

    2.  If the client´s in-house is responsible, he/she likely get´s back with clarifying questions about the data points or requires additional findings.

4.  Final write up delivered in Google Doc.

You are expected to collaborate closely with either our business writer or the customer during this process. This includes:

-   Answering questions left in the Google Doc by customers and our business writer.

    -   Use the comment function on Google Docs to answer, ask questions or to clarify any points.

-   Providing missing data points or calculations needed for sections of the report. Please leave a comment or provide an answer that the calculations were provided. Feel free to add the numbers directly into the draft write-up.

-   Be as specific as possible when answering.

-   Respond in a timely and friendly manner.

-   Adding the edited titles to the various plots have been a friction point in the latest projects. Therefore, please make sure all the correct titles have been added to the correct plots and knitted properly. When doing so, please leave a comment in Google Doc that the titles have been added for a particular plot e.g. "title added to the plot in the script". That way, we can clear the comment and create a new html file with the new plots.

------------------------------------------------------------------------

## 5 Communication

Communication is very important to us during the data analysis process. To avoid emails, skype, whats app etc. messages flying around, we prefer to have everything centralised in slack. While it may take some time to get used to it, we´re confident that the long-term benefits outweigh the short term pains.

Please join slack through the following link: <https://join.slack.com/t/frontpage-data/shared_invite/zt-k6hp6qeo-eXrs2T5ccMi4OLnBmLf4Ag> 

To share longer commentary, record a [Loom](https://loom.com/) video. To get clarity, hope on a Zoom/Skype call (see below for contact details).

\
**Please provide status updates every 3 days**

-   Help the team to estimate how we're doing on time.

-   This removes unnecessary stress and pressure, especially if there's a slow-down.

```{=html}
<!-- -->
```
-   a simple one-liner will suffice.

    -   For example, "Making progress on Section X" or "Received your specification, will be able to look at them on Monday."

------------------------------------------------------------------------

## Contact Details

[daniel.kupka\@frontpagedata.com](mailto:daniel.kupka@frontpagedata.com) or +49163 6979372 for Whatsapp or calls. To schedule zoom/skype meetings, please go to: <https://calendly.com/danielkupka/15min> If a time does not suite you there, let me know and I can make myself available.

------------------------------------------------------------------------

## Questions/Suggestions?

If you have any questions about the process or anything else, please let me know.

Also, if you think there are better ways to structure/organize the template/reports, I more than happy to implement your changes to allow for a smoother work flow experience.

Excited to be working with you! 🚀

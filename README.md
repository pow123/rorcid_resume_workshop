# Creating a Resume in RStudio using rorcid

## About the Workshop

### Description:
An ORCID profile is a useful solution to author ambiguity.  It can be used to create an NIH biosketch and help consolidate all your research output in one online profile.  In this advanced workshop, participants will work with the R packages RORCID and VITAE in RStudio to create a resume based on a template ORCID profile.  A basic understanding of R, RStudio, and installing packages is necessary for optimal workshop experience.  Maximum attendance is 25.

### Requirements:
Requires introductory knowledge of R and working with APIs. Requires R and RStudio installed on the computer being used.

### Facilitator:
Peace Ossom-Williamson, Director for Research Data Services, The University of Texas Arlington (Twitter: [@123POW](https://twitter.com/123POW))
- Website: https://peaceossom.com
- ORCID: https://orcid.org/0000-0001-6229-7514


### Credits: 
The following creators are credited for their output which are utilized in this workshop:
- Tamara Sternlieb – [CV via rorcid and vitae](https://github.com/TamiSter/AwesomCVwithORCID)
- Scott Chamberlain et al. - [rorcid R package](https://github.com/ropensci/rorcid)
- Mitchell O'Hara-Wild - [vitae R package](https://github.com/mitchelloharawild/vitae)

---
## Steps

### Access and Setup:
Information about ORCID data can be found at the following links:
- ORCID API Documentation (click “What sections can I read on ORCID record using the API?”) at
  https://info.orcid.org/documentation/api-tutorials/api-tutorial-read-data-on-a-record/#easy-faq-2361
- rorcid walkthrough: https://ciakovx.github.io/rorcid.html 

❗🔥For the workshop to be successful, the following installations/updates must occur:🔥❗
- [R](https://www.r-project.org/) must be updated with version 4.0 or later
- [RStudio](https://rstudio.com/products/rstudio/download/) must be updated with 1.4 or later
- Install or update tinytex using steps at https://yihui.org/tinytex/r/#debugging

### Getting Started:
1. Download the repository from https://github.com/pow123/pow123-rorcid_resume_workshop
2. Unzip the folder.
3. If you'd like to add your headshot, upload it into the **rorcid_resume_workshop** folder. Make sure to save it as `ProfilePic.jpg`.
4. Open RStudio and select “New Project.” Then select “Existing Repository.”
5. Open the `ORCID-CV.Rmd` file.
6. Load the following packages:
  * `library(rorcid)`
  * `library(httpuv)`
*For the libraries you need to install, first use `install.packages()` before loading libraries.*

### Updating Your ORCID Profile:
Visit your ORCID profile and make sure it is up-to-date. You can also use `browse(as.orcid("YourORCID")`, replacing "YourORCID" with your ORCID number in quotes, to open your profile from RStudio.

Make sure to provide education and experience and link your ORCID profile with relevant publications.

### Authenticating with ORCID:
7. First, make sure you are logged into ORCID.
8. Next, use `orcid_auth()` and a new browser window will open telling you that authentication was successful and to come back to R.
9. In the console a "Bearer" alphanumeric code will appear. Copy the alphanumeric code.
10. Next, in the console, load the `usethis` package and modify your Renvironment: 
  ```{r }
  #Input install.packages("usethis") to install the package first.
  library(usethis)
  usethis::edit_r_environ("project")
```
  *This is to edit the R environment of this project alone, but you can use “user” instead.*
11. A new window will open in the text editor which will be called `.REnviron`.
12. In the new window, write the following:
```{r }
  # Replace your_alphanumeric_code below with the code you copied before. 
  # Make sure to include quotation marks.
  ORCID_TOKEN="your_alphanumeric_code"
```
13. Next restart your R session. (How? Go to the menu at the top of RStudio, and select Session--> Restart R.)
14. 


Shield: [![CC BY 4.0][cc-by-shield]][cc-by]

This work is licensed under a
[Creative Commons Attribution 4.0 International License][cc-by].

[![CC BY 4.0][cc-by-image]][cc-by]

[cc-by]: http://creativecommons.org/licenses/by/4.0/
[cc-by-image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[cc-by-shield]: https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg

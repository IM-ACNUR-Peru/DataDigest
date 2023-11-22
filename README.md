# DataDigest


## Automation of Report Generation

The Rmd is knotted on a weekly basis and the files shared via various channels - email/teams/sharepoint

It is set up here to allow for automation with a direct connection to UNHCR kobo server using an authentication token.

Below is a step by step how to in order to configure the automation.

See also - https://posit.co/blog/git-backed-deployment-in-posit-connect/ & https://docs.posit.co/connect/user/git-backed/#updating-content

 
### Step 1 - Set up and/or refresh the `manifest.json`

You first need to create a documentation file - which allow the Rstudio server to regenerate your report. This files is created by th e `rsconnect::writeManifest`.

Note that if you are the one developing any of this package, you will first need to re-install them from github or gitlab for the manisfest file to be correctly written. See more documentation here: [Git Backed Content - RStudio Connect: User Guide](https://docs.rstudio.com/connect/user/git-backed/)

```
rsconnect::writeManifest(appPrimaryDoc = "Weekly_Data_Digest.Rmd")
```

### Step 2 -  Publish the report to Rstudio Connect from Github

Go to UNHCR Rstudio server - [http://rstudio.unhcr.org](http://rstudio.unhcr.org) - you need first to have a license associated to your account - Contact Global Data Service Data Science team for that.
 
![ ](https://raw.githubusercontent.com/unhcr-americas/weekly-report/main/inst/fromGit.png) 



![ ](https://raw.githubusercontent.com/unhcr-americas/weekly-report/main/inst/fromGit2.png)


![ ](https://raw.githubusercontent.com/unhcr-americas/weekly-report/main/inst/fromGit3.png)



### Step 3 -  Set up your kobotoolbox API key within Rstudio Connect

You need now to set up the kobotoolbox authentication token within the Rstudio server so that the server can actually pull the data from Kobotoolbox in order to regenerate the Report.

![ ](https://raw.githubusercontent.com/unhcr-americas/weekly-report/main/inst/fromGit4.png)

![ ](https://raw.githubusercontent.com/unhcr-americas/weekly-report/main/inst/fromGit5.png)


![ ](https://raw.githubusercontent.com/unhcr-americas/weekly-report/main/inst/fromGit6.png)


### Step 4 -  Set up report frequency generation and sending it to your email


![ ](https://raw.githubusercontent.com/unhcr-americas/weekly-report/main/inst/fromGit7.png)

et voila...


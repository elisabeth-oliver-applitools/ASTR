This repo contains 3 things, currently:
1. This README - an abriviated guide on the basics of ASTR
2. Demo - a simple ASTR project demonstration with three tests inside, demonstrating how:
    - simple tests are written
    - web crawling
    - logging in with variables
3. A Quick Setup Guide - how to go from a text editor and java to a ASTR webcrawler
4. Applitools Simple Test Runner Documentation(6/10/22) - A copy of the official docs, uploaded on 6/10/22 from their official home on google docs.

-----

The following is a summary of key points in working with ASTR. 
Please see the official documentation for further details : 
https://docs.google.com/document/d/1Gradtg5pNCIGh-7bB7u_PImmGam7lof-duqbVxmDYdU/edit?usp=sharing

Or if you are unable to access this link see the copy in this repository (Applitools Simple Test Runner Documentation). 

ASTR Projects are made up of 3 core files:
1. A "job" file (in this case job.xml) which contains the
    testing flow
2. The applitoolsConf.xml which contains specific information about the testing environment,
    specifically your API key
    - See "Applitools Configuration Settings" in the documentation for more details on these options.
3. The ApplitoolsSimpleTestRunner.jar - the java program which will run the previously mentioned job.
    - Links to the most recent version of ASTR (as well as a record of past versions) can be found at 
      the bottom of the ASTR documentation under "Versions"

Everything else is optiononal, but generally recomended.
Among these recomended files are:
- configurations.xml : contains reusable test runner and webdriver configurations.
    - This is where one should define whether on wants to use the UFG, what environments one want to render 
    their checkpoints on, what browser they wish to locally run their tests from, and to set any browser options 
    on chrome or firefox browsers (headless mode, for example) 
    - See "Cleaner & Modular Coding" - "Using Predefined variables/Configurations/Configuration Groups" - 
    "2) Defining External Configurations and Configuration Groups" for more details.
- definitions.xml : contains reusable job actions and variables. 
    - I think of this as being where one's functions and one's data live. 
    - See "Cleaner & Modular Coding" - "Using Predefined variables/Configurations/Configuration Groups" - "1) Defining Variables"
    and "Cleaner & Modular Coding" - "Action Blocks" for more information on how to set variables and 
    reusable instructions respecively.
> It should be noted that ASTR makes no distinction between what I have described as a "definitions" file 
  and a "configurations" file and these can be named whatever you please, this is however an organization 
  split I find helpful as it seperates runner and browser specific configuration from the business logic of running your tests. 
- sitemap.xml : contains a list of urls for a "crawl" action to explore.
    - See "Supported Actions" - "Iterative Actions" - "Crawl a sitemap.xml file" for more information on how to call a crawl action. 
    - See "sitemap.xml" in this project for an example of a valid sitemap.xml file. 


Run ASTR projects from the command line with the command: 

    java  -jar ApplitoolsSimpleTestRunner-3.58.1.jar job.xml


If you encounter a problem while running ASTR and need to do some trouble shooting, either on your own or with any of your dedicated Applitools support resources (Beth, EJ, or any of the support team), you can add any of these flags to have ASTR print some more helpful information:

    “-narrate”          will print out the actions that are executed. 
    
    “-applitoolsLogs”   will print out the logs for the Applitools commands that are executed. 
    
    “-time”             will print out the time it took for each action to be performed. 
    
These can be combined or used individually. For example:

    java  -jar ApplitoolsSimpleTestRunner-3.58.1.jar job.xml -narrate -applitoolsLogs




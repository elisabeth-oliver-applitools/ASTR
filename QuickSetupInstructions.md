Working with ASTR is straight forward but can require learning some syntax. 
To get around that and get simple projects off the ground quickly, ASTR has a quick start wizard which automatically sets up the boilerplate code for you for a couple common situations. 

This tutorial explains how to go from nothing but a text editor and java, to a simple web crawler with ASTR.  


Assumed Initial State:
- you have a text editor (I use Visual Studio Code, but that isn't required)
- you have Java on your machine (version 1.8 or higher)
    - you can check by typing: "java --version" into your console command line

Steps:
1. Go to:

    https://docs.google.com/document/d/1Gradtg5pNCIGh-7bB7u_PImmGam7lof-duqbVxmDYdU/edit?usp=sharing
    
    and navigate to the Versions sections. Download the most recent version. Place this in your working folder 
    
2. Download an appropriate Chromedriver.
- If on a Mac or Linux machine, I recomend using Homebrew as this is the easiest way to keep the driver up to date.
- If not, we'll need to download it manually
    - Check which version of Chrome you are using. In Chrome, go to Settings-> About Chrome. You should see the version there.
    - Go to: https://chromedriver.chromium.org/downloads and download the matching version. Place this in your working folder as well or set it up to be reachable on your PATH.
        
3. Set up ASTR job files:
    - enter to the console: 
    - java -jar ApplitoolsSimpleTestRunner-\<version\>.jar   
    - Select option 2 of the 5 to create a sitemap crawler
    - Enter the values for your project
    
4. Finish Configuring ASTR for your running environment by adding the following to applitoolsConf.xml if appropriate:
    - If you have a private cloud or on-premise server:
        - \<Server\>https://{your-org-here}eyes.applitools.com\</Server\>
    - If you have proxy settings:
        - \<Proxy\>https://proxy.url.com:8080\</Proxy\> OR
    
        - \<proxy username="JohnSmith" password="1234"\>https://proxy.url.com:8080\</proxy\>
    
5. Go to the sitemap.xml file and add the pages you want to test (see the included Demo project for an example of what that should look like)
    
6. Run the command: 
    - java -jar ApplitoolsSimpleTestRunner-\<version\>.jar job.xml


And that's it! 
Like that, you should have a collection of tests uploaded to your Applitools dashboard. 

# seleniumWithJmeterCICDInetgration
This repository describes how to intgerate selenium tests with Jmeter and how to configure these tests with CICD pipeline

# 1.Test-Automation
In this template we are providing two solutions-

1.Integration of Selenium code with Jmeter
2.Intergartion of Jmeter to CI/CD Jenkins

 # 1.Integration of Selenium code with Jmeter
Here, we can integrate our selenium code with Jmeter using the following two methods:

JmeterSeleniumProject.jar [Junit Project jar file] :

1. It must be placed within lib/JUnit
2. Now you need to add Junit plugin in Jmeter using plugin manager.
3. Open Jmeter and add Junit sampler
4. Select the test class name
5. Select Test name [One Test method per Junit Sampler]
6. Add listeners and Run

WebDriver Sampler:
1. Add Webdriver sampler
2. Add Chrome config element and provide your path to the driver
3. Write your script just like how it is written in "SeleniumIntegration.jmc"
4. Add listeners as per your requirement.
5. Downlaod the chrome driver.
6. Provide the path of chrome drive "SeleniumIntegration.jmc" script.


# 2. Integration of Jmeter with CI/CD- Jenkins 

So we already have Jmeter script from the above solution SeleniumIntegration.jmc. I assume that you will be familiar with Jmeter tool for performance testing. Also you can check the blogs series to create script here -https://blog.knoldus.com/recording-of-jmeter-script-part-1/  and check this blog to integrat jmeter with Jenkins -https://blog.knoldus.com/how-to-integrate-jmeter-into-jenkins/  

Now come to the topic.These are prerequisite 

   ### Installation of Jmeter:
1. You can download the Jmeter using - http://jmeter.apache.org/download_jmeter.cgi (choose the binaries zip/tar) 
2. Most importanley that both Jmeter and Jenkins should be insatll on same machine.

   ###  Installation of Jenkins on Local machine-
https://www.digitalocean.com/community/tutorials/how-to-install-jenkins-on-ubuntu-18-04 Using this article you can install the jenkins on your local machine.

  ### Add Plugins in Jenkins- 
In jenkins you have to add 2 plugins for intergration with Jmeter.
Go to Manage Jenkins-->Manage Plugins-->Available .
Search for git and performance plugin and install it

## How to Set-Up Git credentails on Jenkins-
Go to the Manage Jenkins-->Manage Credentials
Click on Jekins Crendials so you will be redirect to Global credentials (unrestricted) page
Click on Add Credentials from left pane.
Add the Git Credentials with SSH username and Private Key.

## How to Import Jenkins Job
Now you have to import the Job in your Jenkins. we have two option to import the job-
1. Use Job Import plugin
2. Just copy the Jmeter folder given above in your Jenkins directory like-
   * Go to the path - var/lib/jenkins/jobs
   * Paste the Jmeter folder inside it.
   * Now you will get this job in your Jenkins
     
## How Jmeter script work here-
   * I assume that you have already clone this job in your local. Now you can see the SeleniumIntegration.jmc scrit in your local.
   * Next when you run the job , Jenkins will clone the jmeter script in your local workspace  of Jenkins.
   * And then jekins will run the jmeter script automatikally and save the results in your workspace.
  
## How to run Jenkins Job- 
 1. Click on the job -Jmeter
 2. Click on Build with parameter from left pane.
 3. Pass the paarmeter value-
 4. Run the build.
 

 
 
 ## Report & Results
 1. Click on the current build number from build history 
 2. Click on the Performance Trend- you will see teh graph and test results of script.
 3. You can also check teh html report inside the workspace of jmeter .
 
 
 Note- In this Jmeter folder -config file you can update the report path as per your system


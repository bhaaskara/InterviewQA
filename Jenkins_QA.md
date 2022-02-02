# What is pipeline ?
Jenkins Pipeline (or simply “Pipeline”) is a suite of plugins which supports implementing and integrating continuous delivery pipelines into Jenkins.

# Jenkins pipeline: agent vs node ?
The simple answer is, **Agent** is for **declarative** pipelines and **node** is for **scripted** pipelines.

# Copy data from one jenkins agent to another 
- use plugin - publish over ssh
- use scp command in ssh step

# What is the difference between Maven, Ant and Jenkins? 
Maven and Ant are Build tools, whereas Jenkins is a continuous integration(CI/CD) tool.

# Explain what is continuous integration? 
When multiple developers or teams are working on different segments of same web application, we need to perform integration test by integrating all the modules. To do that an automated process for each piece of code is performed on daily bases so that all your code gets tested. And this whole process is termed as continuous integration.

# What is the relation between Hudson and Jenkins? 
Hudson was the earlier name of current Jenkins. After some issue faced, the project name was changed from Hudson to Jenkins.

# How you automate the whole build and release process? 
• Check out a set of source code files. 
• Compile the code and report on progress along the way. 
• Run automated unit tests against successful compiles. 
• Create an installer. 
• Publish the installer to a download site, and notify teams that the installer is available. 
• Run the installer to create an installed executable. 
• Run automated tests against the executable. 
• Report the results of the tests. 
• Launch a subordinate project to update standard libraries. 
• Promote executables and other files to QA for further testing. 
• Deploy finished releases to production environments, such as Web servers

The above process will be done by Jenkins by creating the jobs.

# How you will take backup for Jenkins? 
Copy JENKINS_HOME directory and “jobs” directory to replicate it in another server.

# In how many ways you can install the Jenkins? 
We can install Jenkins in 3 Ways 
• By downloading Jenkins archive file 
• By running as a service Java –jar Jenkins.war 
• By deploying Jenkins.war to the webapps folder in tomcat.


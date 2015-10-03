# devops-project

### Build section
## Setup

* Forked Apache Java Mavens project titled 'commons-csv'. The following is the link to the forked repository:


* Used Jenkins as the build server. To install Jenkins, we have used the following command:
```
brew install jenkins
```
* The following plugins were intalled in Jenkins:
GIT plugin
Email Extension plugin
Mail Watcher plugin
Multi-Branch Project plugin
Post-Build scripts plugin

* Added the Maven, JDK installation paths in the Jenkins System settings.

* Added the smtp server value=smtp.gmail.com

* Added the user name and password for smtp authentication using ssl protocol and smtp port 465.

* Added the default recipients for the email.

* To be able to send emails in Mac you need to start postfix using the following command:
```
sudo postfix start
```
And in the gmail account used for sending the email, turn off safety. 

* Create Maven multi-branch project titled 'commons-csv' in Jenkins.

* In Source Code Management section in the configuration of the project do the following: 

* Blank the Sync Branches Schedule textbox in the configuration of the project. 

* Select the Git option and then enter the path of the local Git repository using:
  file://

* Specify the Git branches from the project to be included and excluded.

* Remove all the default build triggers.

* In the build step, specify the goals and options:
```
clean install
```
* Add the following post-build steps:
Email Notification
Add the always trigger, so that mail is sent everytime build is triggered. Also add the recipients list. 

Post-build scripts
Add the following script in build steps:
```
#!/bin/bash
open http://localhost:8080/view/All/builds
```

Aggregate downstream test results
Generates a file containing all the tests. 

##Capabilities

* Create a post-commit file in .git/hooks and place the following script inside
```
#!/bin/bash
branch_name="$(git symbolic-ref --short HEAD 2>/dev/null)" ||
branch_name="(unnamed branch)"

url='http://localhost:8080/job/commons-csv/branch/'${branch_name}'/build'
curl $url
``` 

Team: 
Gauri Naik (gnaik2)
Arvind Telharkar(adtelhar)
Ravneet Kaur(ravnee)














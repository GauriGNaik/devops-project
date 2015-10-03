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

* Select the Git option


##Capabilities

* 














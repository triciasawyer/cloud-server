# cloud-server

## Project

Lab 16 - intro to AWS

## Collaborators

Stephen Clemmer and Ryan Gallaway

## Live deployment links

[GUI](http://cloudserver-env.eba-2p3krtgt.us-east-2.elasticbeanstalk.com/)
[CLI](http://cloud-server-dev.us-east-2.elasticbeanstalk.com/)

### AWS IAM

you will need to have at least one user with an access key and secret key added to the command line.

Go to IAM
If no user exists, create one. follow the prompts in the GUI
give that user permissions create group (or not).
permissions for lab 16: AdministratorAccess-AWSElasticBeanstalk

#### To manage the Access Key

go to the users tab in IAM
select your user
notice the tabs: Permissions | Groups | Tags | Security credentials
select Security credentials
create an access key. yes a CLI access key
note: once created, you will not be able to view the secret key again
go to the terminal
run the command aws configure. follow instructions... basically
paste in your access key. press enter
paste in your secret key. press enter.
select your region
default output leave as is
Your Server Code

confirm that your package.json is in order.
main should be assigned the appropriate file name as an entry point
start script should be present and also point to your file entry point
zip ONLY the necessary files for GUI deployment. class example: package.json and server.js

#### To deploy via elastic beanstalk in the GUI

Go to Elastic beanstalk in console (use search bar or recently visited)
select the orange create application button
name your application (unique to your account)
platform, select node.js
platform branch, use default of node 18
platform version use default provided
no need to add tags
select Upload your code
confirm you have a zip file with ONLY package.json and your code.
NO node modules or package-lock.json
choose file and upload
you are done making selections, click the orange create application button

### AWS Elastic Beanstalk

to deploy via elastic beanstalk in the CLI

eb init
use default names, select region, no need to add SSH
eb create
use default names, select region, no need to add "extras" with thee y/n questions
that's it. note: create ALSO deploys code
if you need to update your code, run eb deploy

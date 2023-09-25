# Cloud-server with AWS

## Live deployment links

[GUI](http://cloudserver-env.eba-2p3krtgt.us-east-2.elasticbeanstalk.com/)
[CLI](http://cloud-server-dev.us-east-2.elasticbeanstalk.com/)

### AWS IAM

Need to have at least one user with an access key and secret key added to the command line.

- Go to IAM
- If no user exists, create one. follow the prompts in the GUI
- Give that user permissions to create group (or not).
- Permissions for this project: AdministratorAccess-AWSElasticBeanstalk

#### Managing the Access Key

- Go to the users tab in IAM and select your user. Notice the tabs: Permissions | Groups | Tags | Security credentials
- Select Security credentials and create an access key (CLI access key).
note: once created, you will not be able to view the secret key again
- In the terminal, run the command aws configure. follow the instructions (paste access key, then secret key, region, leave default output, server code).
- Confirm the package.json is in order.
- Main should be assigned the appropriate file name as an entry point and the start script should be present and also point to your file entry point
- Zip ONLY the necessary files for GUI deployment (ex. package.json and server.js)

#### To deploy via elastic beanstalk in the GUI

- Go to Elastic beanstalk in console (use search bar or recently visited)
- Select the orange create application button and name your application (unique to your account)
- Platform, select node.js
- Platform branch, use default of node 18
- Platform version, use default provided (no need to add tags)
- Select Upload your code, confirm you have a zip file with ONLY package.json and your code (NO node modules or package-lock.json)
- Choose file and upload
- Click orange create application button

### Deplpoying AWS Elastic Beanstalk in CLI

- `eb init`
- Use default names, select region, no need to add SSH
- `eb create`
- use default names, select region, no need to add "extras" with the y/n questions
- Note: create will ALSO deploy code
- If you need to update your code, run `eb deploy`

# cfn-linux_rstudio
Cloudformation template (JSON) for a Linux box with RStudio installed

Included is a simple bash script, provisionCloudFormation, which is just a wrapper around the cloudformation CLI.
Example with your template in the current directory:
    ./provisionCloudformation.sh dixonaws@amazon.com cfn-linux_rstudio.template.json

You can tear down a stack using the cloudformation CLI:
    aws --profile dixonaws@amazon.com --region us-east-1 cloudformation delete-stack --stack name [foo]

Of course, you'll need to define your AWS credential in your profile, per http://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html

The template creates the following resources:
<ol type="1">
<li>Linux with R Studio</li>
  <ol type="a">
  <li>Ubuntu 14.04</li>
  <li>RStudio 1.10</li>
  <li>R 2.11.1</li>
  
  </ol>

The only parameter supported is KeyName: the name of the private key that will be used to access the instances created by the template. This key must exist before running the template.

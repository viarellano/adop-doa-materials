# What is DevOps Academy?
The DevOps Academy is a two-day training course that aims to provide a practical introduction to the tools commonly used in the world of DevOps and Continuous Delivery. With a focus on lab-based learning, participants will be introduced to, and experience first-hand, the latest advanced engineering techniques which, when applied, can apply a huge benefit to project delivery.

This repository contains materials and files required during the various phases of the course. It is recommended that you clone this repository to your local machine as a pre-requisite for the course.

The repository contains:
- Standing Up Tools
- Cartridge Collections
- Platform Extension Collections
- Miscellaneous files required for the lab modules

## How to stand up a DevOps Academy stack via CLI
In order to stand up the DevOps Academy stack located under the Standing_Up_Tools folder you can run a simple AWS CLI command:
```
aws cloudformation create-stack --stack-name DOA-Stack --template-body <REPO_FILE_PATH>/doa_stack.json --disable-rollback --parameters ParameterKey=AdopUsername,ParameterValue=<YOUR_USERNAME> \
ParameterKey=AdopUserPassword,ParameterValue=<YOUR_PASSWORD> \
ParameterKey=AwsAccessKey,ParameterValue=<AWS_ACCESS_KEY> \
ParameterKey=AwsSecretKey,ParameterValue=<AWS_SECRET_KEY> \
ParameterKey=KeyName,ParameterValue=<YOUR_SSH_KEY>
```

The < > symbols surrounding any values in the above command indicate that they require to be replaced. This table showcases explanations of said values:

| Value to be replaced | Explanation | Example value |
| --------|---------|-------|
| <REPO_FILE_PATH> | File path of where your adop-doa-materials repository lives and its subsequent doa_stack.json|C://Users/YourUser/Documents/Repos/adop-doa-materials/Standing_Up_Tools|
| <YOUR_USERNAME> | The username you will use to log into any ADOP/C tools|Admin|
| <YOUR_PASSWORD> | The password you will use to log into any ADOP/C tools|password123|
| <AWS_ACCESS_KEY> | The AWS access key of the account you are launching this stack from |EXAMPLE_ACCESS_KEY|
| <AWS_SECRET_KEY> | The AWS secret key of the account you are launching this stack from |EXAMPLE_SECRET_KEY|
| <YOUR_SSH_KEY> | An SSH key you have made in EC2 that you will use to log into the ADOP/C instance that this stack stands up |MY_SSH_KEY|

After you have finished using this cloud formation stack and no longer require to have it stood up you can use another AWS CLI command to delete it:
```
aws cloudformation delete-stack --stack-name DOA-Stack
```

## How to stand up a DevOps Academy stack via the AWS Console
This section describes how you can stand up the DevOps Academy stack using the Standing_Up_Tools/doa_stack.json file through the AWS console web UI.
1. Log into your AWS account via any browser
2. Navigate to the CloudFormation service
3. Click on the blue "Create Stack" button
4. Under the "Choose a template" section click the "Choose File" button
5. Navigate to your repository and open the Standing_Up_Tools/doa_stack.json file
6. In the "Stack name" field enter "DOA-Stack"
7. Under the "Parameters" section fill in each field appropriately - use the table constructed in the above section for explanations of each parameter
8. Press the blue "Next" button twice
9. On the final screen review all of the details you have put in and press the blue "Create" button
10. If everything goes successfully you should eventually see your stack be stood up successfully

You can delete the stack at anytime in the console by navigating back to the CloudFormation service, finding the "DOA-Stack", right clicking it and selecting "Delete Stack".

# License
Please view [license information](LICENSE.md) for the software contained on this image.

# User feedback

## Documentation
Documentation will be captured within this README.md and this repository's Wiki.

## Issues
If you have any problems with or questions about this image, please contact us through a [GitHub issue](https://github.com/Accenture/adop-doa-materials/issues).

## Contribute
You are invited to contribute new features, fixes, or updates, large or small; we are always thrilled to receive pull requests, and do our best to process them as fast as we can.

Before you start to code, we recommend discussing your plans through a [GitHub issue](https://github.com/Accenture/adop-doa-materials/issues), especially for more ambitious contributions. This gives other contributors a chance to point you in the right direction, give you feedback on your design, and help you find out if someone else is working on the same thing.
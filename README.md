# aws-stl-meetup

Recommendations for the AWS STL Meetup CloudFormation workshop:
- an AWS account with a powerful IAM user that has API access keys
- an EC2 key pair named "AWS-STL-Meetup"
- the AWS CLI: https://aws.amazon.com/cli/ with a configured profile
- Visual Studio Code: https://code.visualstudio.com
- the GNU Bash shell and SSH (see below for Windows options)

Template steps:
- 01 Start with a VPC
- 02 Parameterize the VPC CIDR block
- 03 Add a subnet
- 04 Add an EC2 instance and Security Group
- 05 Try adding an Elastic IP
- 06 Add and attach an Internet Gateway
- 07 Open up ICMP
- 08 Add and associate a route table with a default route to the Internet Gateway
- 09 Reorganize and add a private subnet with an empty route table
- 10 Add a private EC2 instance with its own Security Group to the private subnet
- 11 Add a NAT Gateway
- 12 Fix the NAT Gateway allocation ID
- 13 Add a default route through the NAT Gateway to the private subnet

If on Windows, the "stack" shell script could be converted to a batch file or PowerShell script. In a pinch, the "build" commands could simply be run from a command prompt a la `aws --region us-east-2 --profile slalom cloudformation update-stack --tags Key=Name,Value=CFN-AWS-STL-Meetup-13 Key=Owner,Value=astrostl Key=Environment,Value=Demo --stack-name AWS-STL-Meetup-13 --template-body file:///Users/astrostl/src/aws-stl-meetup/AWS-STL-Meetup-13.yaml`, and the PuTTY utility at https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html could be used for SSH connectivity.
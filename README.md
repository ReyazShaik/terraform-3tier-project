✅ 1. Install Required Tools on Ubuntu EC2 (Jenkins Server)
                    **Install Terraform**
sudo apt update
sudo apt install -y gnupg software-properties-common

curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -
sudo apt-add-repository "deb https://apt.releases.hashicorp.com $(lsb_release -cs) main"
sudo apt update
sudo apt install terraform -y


**                    **Install AWS CLI**
**sudo apt install awscli -y


**                      **********Install Git**
**sudo apt install git -y

✅ 2. Add AWS Credentials in Jenkins
Your Jenkinsfile uses credential IDs:
aws-access-key
aws-secret-key
So you MUST create them in Jenkins:

Steps:

Jenkins → Manage Jenkins

Credentials → System → Global

Add Credentials

Add 1st credential:

Kind: Secret text

Secret: your AWS_ACCESS_KEY_ID

ID: aws-access-key

Add 2nd credential:

Kind: Secret text

Secret: your AWS_SECRET_ACCESS_KEY

ID: aws-secret-key


✅ 3. Use the Correct Jenkinsfile


✅ 4. Run the Pipeline
Click Build with Parameters

Choose:

ACTION = apply<img width="1920" height="1080" alt="Screenshot (4)" src="https://github.com/user-attachments/assets/f2f1eb6f-b6fd-4514-9c83-33762b5a4964" />


Terraform will begin creating your VPC, subnets, EC2, RDS, ALB, and S3

<img width="1920" height="1080" alt="Screenshot (4)" src="https://github.com/user-attachments/assets/35f31040-5eec-46c0-9f0a-e80721b62376" />



# Setting Up an EC2 Instance on AWS for LAMP Stack

## Step 1: Sign in to AWS Console

- Go to the [AWS Management Console](https://aws.amazon.com/console/).
- Sign in to your AWS account or create a new one.

## Step 2: Navigate to EC2 Dashboard

- In the AWS Management Console, locate the "Services" dropdown and select "EC2" under the "Compute" section.

## Step 3: Launch an Instance

- In the EC2 Dashboard, click on the "Instances" link in the left navigation pane.
- Click the "Launch Instances" button.

## Step 4: Choose an Amazon Machine Image (AMI)

- Choose "Ubuntu Server" as your AMI. Select the version that is eligible for the AWS Free Tier.
  ![img](/images/aws/1.png)

## Step 5: Choose an Instance Type

- Select the "t2.micro" instance type. This type is eligible for the AWS Free Tier.

## Step 6: Create a Key Pair

- Choose "Create a new key pair" and provide a name. Click on "Create Key Pair" to download the private key file (e.g., `your-key-pair.pem`). Store it in a secure location.
    ![img](/images/aws/2.png)


## Step 7: Configure Security Group

- Use the default security group provided by AWS. It allows basic inbound SSH access.

## Step 8: Configure Instance Details

- For the number of instances, network settings, and user data, use default settings or adjust as needed for your use case.

## Step 9: Add Storage

- Specify the size and type of storage for your instance. The default storage size is eligible for the AWS Free Tier.

## Step 10: Add Tags (Optional)

- Add tags to your instance for better organization and identification. Tags are key-value pairs.

## Step 11: Review and Launch

- Review your configuration settings. Click "Launch" when you are ready.
  ![img](/images/aws/3.png)

## Step 13: Add Inbound Rules
- Create Inbound rules for HTTP, HTTPS, and SSH.
- Create a SSH rule for allowing connection only from your IPv4
- Create HTTP and HTTPS rules for allowing traffic from anywhere
- Refer below screenshots
  ![img](/images/aws/6.png)
  ![img](/images/aws/7.png)
  ![img](/images/aws/8.png)


## Step 13: Connect to Your Instance

- Use the key pair you generated to connect to your instance using SSH. The connection command will look like this:

  ```bash
  ssh -i "your-key-pair.pem" ubuntu@your-instance-ip
  ```
- Refer below screenshots
  ![img](/images/aws/4.png)
  ![img](/images/cmd/1.png)

#### Now that you have setup your EC2 instance, check out the link below for how to setup LAMP stack
[Lamp Setup On AWS](/README.md)
  

**Introduction:**
Connecting to an Amazon EC2 instance and configuring it with your AWS account is a fundamental step in managing cloud resources. In this article, we'll explore the process using PowerShell and AWS CLI, catering to both Linux and Windows users.

**Connecting to EC2 Instances Using PowerShell:**

If you are a Windows user, PowerShell provides a convenient way to connect to your EC2 instance. Open a PowerShell session and use the following command:

`ssh -i C:\Path\To\Your\KeyPair.pem ec2-user@your-instance-public-ip `


Replace "C:\Path\To\Your\KeyPair.pem" with the path to your private key file and "your-instance-public-ip" with your EC2 instance's public IP address. Note that the username "ec2-user" is commonly used for Amazon Linux distributions.

**Securing Your Key Pair:**
To enhance security, restrict access to your key pair by setting appropriate permissions. Execute the following command:

```
chmod 600 C:\Path\To\Your\KeyPair.pem

```

This ensures that only the owner has read/write permissions, preventing unauthorized access.


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ykfbfojp16jfoizyntcz.png)

**Configuring EC2 Instances with AWS Account:**
Once connected to your EC2 instance, configure it with your AWS account using AWS CLI. Follow these steps:

**Generate Access Keys:**
In the AWS console, navigate to "Security Credentials."
Generate an access key and secret access key.

**Configure AWS CLI:**
In your EC2 instance terminal, run the following command:

```
aws configure

```
Provide your access key, secret access key, default region, and set the output format to JSON.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/42xfsvw3nyvo9fvyv977.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/3y5ctkpp8mrwe6h50bty.png)

Confirm AWS CLI installation with:

```
aws version

```

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/pelrmbshpfjvh0hr1gtt.png)

Your EC2 instance is now configured to interact with AWS services through AWS CLI.
**Using AWS CLI to Access AWS Services:**

**List S3 buckets in the configured region:**

```
aws s3 ls

```


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/nh8xwiiyu8q8got5au09.png)


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/a09ar1ya46prll0tk8lb.png)

**Create an S3 bucket in the configured region:**

```
aws s3 mb s3://bucketname

```

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/8elzohqh8aqc4ads0pm2.png)



![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/edozgn5cpyeh8guti0wh.png)


**Create an EC2 instance using AWS CLI:**

```
aws ec2 run-instances --image-id ami-xxxxxxxxxxxxxxxxx --instance-type t2.micro

```

Replace "ami-xxxxxxxxxxxxxxxxx" with the desired AMI ID and adjust the instance type accordingly.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/euvfm9g61x7wbg3ezhrk.png)


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/23mvgbl706r3s8lq4br4.png)


**Conclusion:**
By combining PowerShell and AWS CLI, you can seamlessly connect to and configure your EC2 instances, providing a powerful and efficient workflow for managing your AWS resources.

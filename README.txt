Directions for creating EC2 instance:
Sign in to the AWS Management Console and open the Amazon EC2 console
Select a region
Choose Launch Instance
Choose a name - SWE-645
Select an Amazon Machine Image (AMI) - Amazon Linux
Choose an instance type - t.2 micro
Select key-pair name - RSA/.pem
Select default security group
Add in security group to allow public access
Select default storage
Launch instance

Directions for creating S3 bucket:

Sign in to the AWS Management Console and open the Amazon S3 console at https://console.aws.amazon.com/s3/.
Choose Create bucket.
Enter the Bucket name (S3 buckets) - swe645-js93 
Choose the Region where you want to create the bucket - Northern VA.
Choose default settings.
Create bucket.

Enable static website hosting:
Open the Amazon S3 console at https://console.aws.amazon.com/s3/.
In the buckets list, I choose the name of the bucket I'm enabling.
Choose properties.
Under static website hosting, choose edit.
Choose use this bucket to host a website.
Under static website hosting, choose enable.
Enter the index document file.
Save changes.

Edit Block Public Access:
Go to permission settings of S3 bucket
Go to block public access (bucket settings), choose edit.
Uncheck block all public access.
Save changes.

Download web server:
Connect to EC2 instance
Download Apache web server in the CLI
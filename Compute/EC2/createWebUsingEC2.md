# Building an EC2 Instance and Creating a Website with S3

## Introduction
This lab is designed to walk you through logging into the AWS console, building your first EC2 instance and S3 bucket, and then creating a website with that bucket!

## Solution
1. Log in to the AWS Management Console using the credentials provided on the lab instructions page.
2. Download the HTML file from GitHub that will be needed in the third objective of the lab: [https://github.com/linuxacademy/content-aws-overview-of-aws.git](https://github.com/linuxacademy/content-aws-overview-of-aws.git). Optionally, create your own HTML file to use instead, if you would like.

### Create an Amazon Linux EC2 Instance
1. In the AWS Management Console, click on Services in the upper left-hand corner.
2. On the menu that appears, select EC2.
3. On the EC2 landing page, scroll down and click Launch Instance > Launch Instance.
4. On the EC2 build page, under Name, type in Webserver or your own name for your instance.
5. Under Instance Type, click on the dropdown menu and choose t3.micro.
6. Under Key pair, click Create new key pair.
7. In the Create key pair box that appears, in the Key pair name box, type Example, or your own name for the key pair.
8. Click Create key pair to save.
9. In the Network Settings section, check the box next to Allow HTTP traffic from the internet.
10. Above that, next to Allow SSH traffic from, click the dropdown next to Anywhere to change it to My IP.
11. Leave everything else as the default, and click Launch instance in the bottom right.
12. Note: It may take a minute or so for the instance to start running.
13. Go to your new instance by clicking the link to the instance in the parentheses after Successfully initiated launch of instance.
14. You should see your Webserver instance as the only item in the list, and you should see Running in green under Instance state.

### Create an S3 Bucket
1. Click AWS in the top left corner of the console to return to the console home page.
2. Click on Services in the upper left-hand corner of the AWS Management Console.
3. On the menu that appears, select Storage on the left panel, and then S3 on the right panel.
4. On the S3 landing page, click Create bucket in the top right.
5. In the Bucket name field, type in a unique name (ex: acgtestbucket31).
6. Note: Your bucket name must be globally unique, so if you get a message stating that your name is already taken, just add some numbers to the end of it.
7. Uncheck Block all public access by clicking the checkmark next to it.
8. Click the checkbox next to the I acknowledge statement in the warning box that appears below that section.
9. Leave everything else as the default, scroll down, and click Create Bucket. Your bucket should appear as the only item in the list.
10. Click on the name of your bucket to get to the main page of your bucket, and to, optionally, see what features are available for your bucket.

### Create a Website Using S3
1. On your bucket's main page, make sure you are on the Objects tab, and click on Upload.
2. From the Upload page, click Add files.
3. Find the HTML file that you downloaded for the lab from wherever you saved it.
4. Note: See the Solution section of this lab guide (above) or the Additional Resources section of this lab page, if you have not already downloaded the HTML file.
5. Select the HTML file and click Open.
6. You can confirm that it is the correct file and correct destination: HoL HTML page.html should appear under Name, and your bucket name should appear under Destination.
7. Click Upload at the bottom of the page.
8. Click Close in the upper right.
9. Click the checkbox to the left of HoL HTML page.html.
10. Click Open in the menu bar under Objects.
11. Your newly created static website should appear in a new tab.

## Conclusion
Congratulations — you've completed this hands-on lab! 
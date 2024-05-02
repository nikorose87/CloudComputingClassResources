# Create a Virtual Private Cloud (VPC) and Launch an EC2 Instance

## Introduction

In this hands-on lab, you will create a new custom Virtual Private Cloud (VPC) and launch a new EC2 instance inside of it!

## Solution

### Log in to the AWS Management Console

1. Log in to the AWS Management Console using the credentials provided on the lab instructions page. 
2. Make sure you're using the `us-east-1` Region.

### Create a New Virtual Private Cloud (VPC)

1. In the search bar at the top of the AWS portal, type and select `VPC`.
2. Click `Create VPC` in the upper left corner.
3. Under `Resources to create`, ensure `VPC and more` is selected.
4. Under `Name tag auto-generation > Auto-generate`, enter `Example`.
5. Review the structure of the VPC in the `Preview` section: the subnets, route tables, and network connections.
6. Under `IPv4 CIDR block`, update the number of bits in the address to 24 (e.g., `10.0.0.0/24`).
7. Scroll down to `Number of Availability Zones (AZs)` and select `1`.
8. Under `Number of public subnets`, select `0`.
   - Note: Notice how the `Preview` changes as you make updates to the VPC settings.
9. Leave the other settings at default, and click `Create VPC`.
10. Once the VPC resources are created, click `View VPC`.

### Launch an EC2 into the Newly Created VPC

1. In the search bar at the top of the AWS portal, type and select `EC2`.
2. Under `Launch instance`, click on the dropdown menu and select `Launch instance`.
3. Under `Name`, enter `Lab Example`.
4. Under `Application and OS Images (Amazon Machine Image) > Quick Start`, ensure the `Amazon Linux` tile is selected.
5. Under `Instance type`, ensure `t2.micro` is selected.
6. Under `Key pair (login)`, click `Create a new key pair`.
7. In the `Create key pair` pop-up menu under `Key pair name`, enter `Lab Example`.
8. Leave the other settings at default and click `Create key pair`.
9. Under `Network settings > Firewall (security groups)`, ensure `Create security group` is selected.
10. Ensure `Allow SSH traffic from` is selected. Then, click on the dropdown menu next to it and select `Anywhere`.
11. Under `Configure storage`, ensure `8 GiB` is configured.
12. Leave the other settings at default, and click `Launch Instance`.
13. Once the instance has successfully launched, click on the instance ID at the top of the page.
14. Once the instance is running, click on the instance ID.
    - Tip: You may need to click the `Refresh` icon at the top of the page to see the instance in the `Running` state.
15. Review the VPC ID and subnet ID that you created in the previous objective.

## Conclusion

Congratulations — you've completed this hands-on lab!
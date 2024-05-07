# Configuring Visual Studio Code and AWS Toolkit on Windows

## Step 1: Install Visual Studio Code

1. Visit the [Visual Studio Code download page](https://code.visualstudio.com/download).
2. Click on the 'Windows' button to download the installer.
3. Once the installer is downloaded, run it and follow the prompts to install Visual Studio Code.

## Step 2: Install AWS CLI

1. Visit the [AWS CLI download page](https://aws.amazon.com/cli/).
2. Click on 'Download' for Windows.
3. Run the installer and follow the prompts to install AWS CLI.

## Step 3: Configure AWS CLI

1. Open a command prompt.
2. Run `aws configure` and provide your AWS Access Key ID, Secret Access Key, default region name, and default output format when prompted.

## Step 4: Install AWS Toolkit for Visual Studio Code

1. Open Visual Studio Code.
2. Click on the Extensions view icon on the Sidebar (or press `Ctrl+Shift+X`).
3. Search for 'AWS Toolkit for Visual Studio Code' and click on 'Install'.

## Step 5: Connect AWS Toolkit to AWS Account

1. In Visual Studio Code, click on the AWS Toolkit icon on the Sidebar.
2. Click on 'Connect to AWS'.
3. Follow the prompts to connect to your AWS account.

That's it! You've now configured Visual Studio Code and the AWS Toolkit on your Windows machine.

## Step 6: Verify the Setup by Creating an S3 Bucket and Uploading a File

1. In Visual Studio Code, click on the AWS Toolkit icon on the Sidebar.
2. Expand the 'AWS: Explorer' section.
3. Right-click on 'S3' and select 'Create Bucket'.
4. Enter a unique name for your bucket and select a region, then click 'Create'.
5. Once the bucket is created, expand the 'S3' section, right-click on your new bucket, and select 'Upload to AWS'.
6. Select a file from your local system to upload.
7. Once the upload is complete, you should see the file listed under your bucket in the 'S3' section.

## Step 7: Create a Lambda Function Using AWS CLI

### Step 7.1: Create a Role for Your Lambda Function

1. Open the AWS Management Console in your web browser.
2. Navigate to the IAM (Identity and Access Management) service.
3. Click on 'Roles' in the left sidebar, then click on 'Create role'.
4. Select 'Lambda' as the service that will use this role, then click on 'Next: Permissions'.
5. In the 'Attach permissions policies' page, select the 'AWSLambdaBasicExecutionRole' policy, then click on 'Next: Tags'.
6. (Optional) Add any tags you want, then click on 'Next: Review'.
7. Enter a name for your role, then click on 'Create role'.
8. Once the role is created, click on it in the roles list, then copy the 'Role ARN' from the 'Summary' tab. You'll need this ARN in the next steps.

### Step 7.2: Create a Python Script for Your Lambda Function

1. Open a new file in your text editor and enter the following Python code:

```python
def lambda_handler(event, context):
    # TODO: replace this with your code
    print("Hello, world!")
```
2. Save file as `lambda_function.py`

### Step 7.3: Create a .zip File Containing Your Lambda Function

1. Open a command prompt.
2. Navigate to the directory containing your `lambda_function.py` file.
3. Run the following command to create a .zip file containing your Lambda function:

```bash
zip my-function.zip lambda_function.py
```
### Step 7.4: Create a Lambda Function Using AWS CLI

1. In the command prompt, run the following command to create a new Lambda function (replace `my-function` with the name you want to give your function, and replace `arn:aws:iam::123456789012:role/service-role/MyTestFunction-role-1tgvn973` with the ARN of the role you created):

```bash
aws lambda create-function --function-name my-function --runtime python3.9 --zip-file fileb://my-function.zip --handler lambda_function.lambda_handler --role arn:aws:iam::123456789012:role/service-role/MyTestFunction-role-1tgvn973
```

2. If the command runs successfully, you should see output that includes the configuration details of your new Lambda function.

If you're able to create a Lambda function, then your AWS CLI is working correctly!

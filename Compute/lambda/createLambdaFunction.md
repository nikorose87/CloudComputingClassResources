# Creating a Lambda Function Using the AWS Console

## Introduction

In this hands-on lab scenario, you'll write a Node.js Lambda function that checks a URL (e.g. `www.amazon.com`) and returns the status code that signifies if the website is up and running or down. During this lab, you'll have the opportunity to explore the Lambda console, function code, execution roles, test events, and execution results. AWS Lambda allows you to write concise functions and only worry about your code. Since Lambda is serverless, AWS manages the underlying infrastructure for you.

## Solution

1. Log in to the AWS Management Console using the credentials provided on the lab instructions page. Be sure to use an incognito or private browser window to ensure you’re using the lab account rather than your own.

    > **Note:** Make sure you are in the **us-east-1** (N.Virginia) Region when you work in this environment.

2. In a new browser tab, navigate to the [code](https://github.com/ACloudGuru-Resources/course-aws-certified-developer-associate/blob/main/creating-a-lambda-function-using-the-aws-console/index.js) that has been provided for the lab in the GitHub repository for the course.

### Author Node.js Lambda Function in the AWS Console

1. In the AWS Management Console, type `Lambda` into the search bar at the top of the page, and then click on `Lambda` from the drop-down menu.

2. In the AWS Lambda console, click `Create function` in the top right.

3. On the `Create function` page, leave `Author from scratch` selected.

4. For `Function name`, type in the name `holURLChecker{writeYourName}`.

5. Set the Node.js runtime version to `20.x`.

6. Leave the other defaults, and then expand `Change default execution role` by clicking the arrow next to it.

7. For `Execution role`, leave `Create a new role with basic Lambda permissions` selected.

8. Click `Create function` at the bottom of the page.

    Your Lambda function should now be created.

9. Scroll down to the `Code source` section of the page.

10. Right-click on `index.mjs` and rename it to `index.js`. Now replace the function code with the code from the GitHub repository.

11. Navigate to your tab with the lab GitHub open and copy the following `index.js` code:

    ```javascript
    const https = require('https')
    let url = "https://www.amazon.com"

    exports.handler = function(event, context, callback) {
    https.get(url, (res) => {
          callback(null, res.statusCode) 	
      }).on('error', (e) => {
        callback(Error(e))
      })
    }
    ```

12. Return to the Lambda function page in your other tab. Under `Code source`, delete the existing `index.js` code, and then paste in the code you just copied.

    Make sure your file is named `index.js`.

13. Click `Deploy` in the `Code source` menu bar above it.

    You have now updated your function and deployed the changes.

### Create a Test Event and Execute Lambda

1. In the `Code source` menu bar, click the down arrow next to `Test`, and click `Configure test event`.

2. In the `Configure test event` popup window, for the `Event name`, type `myTestEvent`.

3. Leave the other default values.

4. Click `Save`.

    You have now created your test event.

5. To test the Lambda function, click `Test` again in the `Code source` menu bar.

    Review the output response.

    You should see a response code of `200`, which means the website is up and running. You can also see your function logs and billed duration displayed.

6. Return to the `index.js` tab under `Code source`.

    Optionally, change the URL in quotations next to `let url =` to different (existing or non-existing) website URLs to test out other response codes.

### Verify That CloudWatch Has Captured Function Logs

1. Click the `Monitor` tab above `Code source`.

2. Click `View logs in CloudWatch`.

    This will open a new tab, taking you to the CloudWatch Management Console.

3. In the CloudWatch Management Console, click on the most recent log stream in the `Log streams` section.

    > **Note:** If you tested multiple URLs in the last objective, you will see multiple log streams displayed here. If you just tested the one URL, you will just see one log stream. In that case, click the one log stream displayed.

4. Notice the data below `Log events`, under `Message`.

    You should see the `START` and `END Request Id`, as well as the `Billed Duration`.

## Conclusion

Congratulations — you've completed this hands-on lab!
# Introduction

You are a cloud data engineer, and you have been asked to help reduce storage costs by transitioning S3 objects to cheaper storage classes. You’ve been asked to transition objects to Standard-IA after 30 days, and expire the objects after one year.

## Preparations

### 1. Create an S3 bucket

1. Log in to the AWS Management Console using the credentials provided on the lab instructions page. Make sure you're using the `us-east-1` Region.
2. Navigate to `S3`.
3. Click on `Create bucket`.
4. Enter a unique name for your bucket in the `Bucket name` field.
5. Leave all other settings at their defaults and click `Create`.

## Steps

### 2. Upload an object to the S3 bucket

1. Find and select the S3 Bucket you just created.
2. Find and select `Upload`.
3. Select `Add Files`.
4. Create a file and select a small text file named 'test.txt'.
5. From the `Add Files` screen, finalize your upload by selecting `Upload`.

### 3. Create an S3 lifecycle for the S3 bucket

1. Click on the Destination S3 bucket name to navigate back to the S3 Bucket.
2. Find and select the `Management` tab.
3. Find and select `Create Lifecycle Rule`.

### 4. Add relevant transitions to the S3 lifecycle policy

Adjust the following fields:

- Lifecycle rule name: `my-lifecycle-Rule`
- Select `Apply to all objects in the bucket`.
- Check the `I acknowledge that this rule will apply to all objects in the bucket` box.
- Check the `Move current versions of objects between storage classes` box.
- Check the `Expire current versions of objects` box.
- Select `Standard-IA` for `Choose storage class transitions`.
- Enter "30" for `Days after object creation`.
- Enter "365" for `Days after object creation` under `Expire current versions of objects`.
- Click `Create rule`.

### 5. Verify your lifecycle policy

1. Find and select the S3 Bucket name at the top of the screen to navigate back to the S3 Bucket.
2. Under `Objects` select the file you uploaded.
3. Find the `Object management overview` and verify that the "my-lifecycle-rule" rule is shown under `Expiration rule`.

## Cleanup

### 6. Delete the S3 bucket

1. From the S3 dashboard, find and select the S3 Bucket you created.
2. Click on `Delete`.
3. You'll be asked to confirm the deletion by typing the name of the bucket. Enter the name and click `Confirm`.
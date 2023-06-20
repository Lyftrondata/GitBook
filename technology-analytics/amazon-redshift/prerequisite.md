---
description: >-
  This section describes the prerequisites for connecting Amazon Redshift to
  Lyftrondata. To complete the prerequisites, the user must have admin access to
  Amazon Redshift.
---

# Prerequisite

* Valid AWS account with full control of an S3 bucket
* Valid Redshift account

### Step 1: Create an S3 bucket

1. Log in to your AWS account and navigate to the S3 service.
2. Click on "Create bucket" and follow the prompts to create a new S3 bucket.
3. Take note of the bucket name for later use.

Note: If the S3 bucket specified in the program does not exist, and the access key used has the necessary permissions, the program may create the bucket automatically. However, if the access key does not have the required permissions to create a bucket, the user must create it manually before using it as a data source for Amazon Redshift.

#### Step 2: Add the required bucket policy <a href="#step-2-add-the-required-bucket-policy" id="step-2-add-the-required-bucket-policy"></a>

1. &#x20;In the S3 service, navigate to the newly created bucket and click on "Permissions".
2. &#x20;Click on "Bucket Policy" and paste in the following policy:

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:ListBucket",
        "s3:CreateBucket"
      ],
      "Resource": "arn:aws:s3:::<s3-bucket-name>"
    },
    {
      "Effect": "Allow",
      "Action": [
        "s3:PutObject",
        "s3:GetObject",
        "s3:ListBucket",
        "s3:DeleteObject",
        "s3:GetObjectTagging",
        "s3:PutObjectTagging"
      ],
      "Resource": "arn:aws:s3:::<s3-bucket-name>/*"
    }
  ]
}
```

Replace `<s3-bucket-name>` with the name of the S3 bucket you created in Step 1.

1. Click "Save".

#### Step 3: Obtain AWS Access Key and Secret Key <a href="#step-3-obtain-aws-access-key-and-secret-key" id="step-3-obtain-aws-access-key-and-secret-key"></a>

1. 1.Log in to your AWS account and navigate to the "IAM" service.
2. 2.Click on "Users" and create a new user.
3. 3.Enable "Programmatic Access" and attach the "AdministratorAccess" policy to the user.
4. 4.Click "Create user".

**Note the Access Key ID and Secret Access Key for later use.**

#### Note: <a href="#note" id="note"></a>

* Keep the Amazon S3 bucket and Amazon Redshift cluster in the same AWS region for optimal performance and reduced network latency.
* Ensure the IAM user or role associated with the AWS access key ID and secret access key used to access the S3 bucket has appropriate permissions to access both the S3 bucket and Redshift cluster.



### Quickstart Steps

Do you have questions about how to use the platform? Don't worry; we've got you covered. Simply follow the quickstart instructions [here](./).

### Questions? <a href="#questions" id="questions"></a>

We're always happy to help with any other questions you might have! [Set up a meeting with our experts](https://www.lyftrondata.com/book-a-meeting/).

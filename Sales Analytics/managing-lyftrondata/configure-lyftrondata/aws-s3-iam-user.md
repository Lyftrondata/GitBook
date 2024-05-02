---
description: >-
  Lyftrondata uses AWS S3 bucket to store and get the logos, connector and
  tenant details.
---

# AWS S3/IAM User

**Step 1: Access AWS Management Console**

1. Navigate to the AWS Management Console by visiting https://aws.amazon.com/console/ and sign in with your AWS account credentials.

**Step 2: Create S3 Buckets**

The application requires three S3 buckets: `<your-company-default-bucket-name>`, `<your-company-connectors-bucket-name>`, and a `<your-public-company-logos-bucket-name>` bucket with a public ACL policy attached. Follow these steps to create the buckets:

1. Click on the "Services" menu in the top-left corner of the console and select "S3" under the "Storage" section.
2. Click on the "Create bucket" button.
3.  Enter a name for your buckets according to above suggested `<your-company-default-bucket-name>` and choose the region where you want to create the bucket. Click "Create bucket" to proceed.\
    \


    <figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>
4. Repeat steps 2-3 to create the `<your-company-connectors-bucket-name>` and public `<your-public-company-logos-bucket-name>` buckets, ensuring the desired region for each bucket.
5. For the public `<your-public-company-logos-bucket-name>`, select the bucket after creation and navigate to the "Permissions" tab.
6. Under "Bucket policy," click on "Edit" and paste the following JSON policy:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::your-public-company-logos-bucket-name/*",
            "Condition": {
                "IpAddress": {
                    "aws:SourceIp": "YOUR-OFFICE-PUBLIC-IP/32"
                }
            }
        }
    ]
}
```

Replace `<your-public-company-logos-bucket-name>` with the name of your public logos bucket.

7. For the connectors bucket, repeat the 5 and 6 steps and use the below JSON policy:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "AllowPublicRead",
            "Effect": "Allow",
            "Principal": {
                "AWS": "*"
            },
            "Action": [
                "s3:GetObject",
                "s3:GetObjectVersion"
            ],
            "Resource": "arn:aws:s3:::<your-company-connectors-bucket-name>/*",
            "Condition": {
                "IpAddress": {
                    "aws:SourceIp": "YOUR-OFFICE-PUBLIC-IP/32"
                }
            }
        }
    ]
}
```

7. Click on "Save changes" to apply the policy.

**Step 3: Verify Setup**

You can verify the setup by navigating back to the "Buckets" dashboard in the S3 service of the AWS Management Console. Ensure that all three buckets (`<your-company-default-bucket-name>`, `<your-company-connectors-bucket-name>`, `<your-public-company-logos-bucket-name>`) are listed.

**Step 4: Create Policy:**

Once logged in, navigate to the IAM Policies in aws console.

* In the policy section, go to create policy and paste the following JSON policy template into the editor:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "s3:*"
            ],
            "Resource": [
                "<your-company-default-bucket-arn>",
                "<your-public-company-logos-bucket-arn>",
                "<your-company-connectors-bucket-arn>",
                "<your-company-default-bucket-arn>/*",
                "<your-public-company-logos-bucket-arn>/*",
                "<your-company-connectors-bucket-arn>/*"
            ]
        }
    ]
}
```

**Step 5: Create IAM User:**

* In the IAM dashboard, click on "Users" in the left sidebar.
* Click on the "Add user" button.
* Enter a username for the new IAM user.
* Choose "Programmatic access" as the access type.
* Click on "Next: Permissions".

**Step 6: Attach Custom Policy**:

* On the permissions page, click on "Attach existing policies directly".
* Search for the custom policy you just created in the policy list.
* Check the checkbox next to the policy.
* Click on "Next: Tags".
* (Optional) Add any tags if required.
* Click on "Next: Review".

**Step 7: Review and Create IAM User**:

* Review the details of the IAM user and the attached policy.
* Click on "Create user".

**Step 8: Complete the User Creation**:

* After the user is created, you will see a success message.
* In the users click on your user which you have just created. Go to security credentials tab and create access key.
* Take note of the access key ID and secret access key provided. These credentials will be used by the IAM user to authenticate with AWS services programmatically.

**Step 9**: **After user and bucket creation**

* Follow the lyftrondata installation [document](../lyftrondata-installation/) for installation.

# AWS S3 Pre-signed URL with AWS Cognito Auth and Encrypted S3 Data

This repository contains documentation on setting up a solution that leverages AWS S3 pre-signed URLs, AWS Cognito for authentication, and AWS KMS for data encryption.

## Services Used

- **AWS S3:** Highly scalable object storage service for data storage.
- **AWS KMS:** Managed service for encryption and decryption of data.
- **AWS Cognito:** User management and authentication service.
- **IAM:** Identity and Access Management service for user, group, and permission management.

## Implementation Phases

### Phase 1: Setup AWS S3 Pre-signed URL

1. Create an S3 bucket.
2. Upload a file to the bucket.
3. Generate a pre-signed URL for the uploaded file.

### Phase 2: Setup AWS Cognito for Authentication
1. Create a Cognito user pool.
2. Create a Cognito identity pool.
3. Create a Cognito user group.

### Phase 3: Combine Auth and Pre-signed URL for Access

1. Create a Cognito user.
2. Log in to the Cognito user pool with user credentials.
3. Use the pre-signed URL to access the S3 bucket file.

### Phase 4: Encrypt Data with AWS KMS Before Uploading to S3

1. Create a KMS key.
2. Define a KMS key policy to enable encryption and decryption for Cognito users.
3. Encrypt the data using the KMS key before uploading it to the S3 bucket.

### Phase 5: Add Monitoring to the Solution (TBD)

In this phase, you can implement monitoring for various components of the solution:

- S3 bucket health
- Cognito user pool health
- KMS key health
- Pre-signed URL usage and requests
- S3 bucket data storage metrics

## Usage Instructions

### Phase 1: Setup AWS S3 Pre-signed URL

To create a pre-signed URL for an S3 object, use the AWS CLI or SDKs. For instance, the following AWS CLI command generates a pre-signed URL for a file named `my-file.txt` in the bucket `my-bucket`:

```bash
aws s3 presign s3://my-bucket/my-file.txt
```

### Phase 2: Setup AWS Cognito for Authentication

Cognito user pool, identity pool, and user group creation are essential for user authentication and access management.

### Phase 3: Combine Auth and Pre-signed URL for Access

After setting up Cognito, use it to authenticate users and grant them access to pre-signed S3 URLs. Obtain the user's ID token from Cognito and use it to generate a pre-signed URL.

### Phase 4: Encrypt Data with AWS KMS Before Uploading to S3

Utilize the KMS key to encrypt data before uploading it to the S3 bucket. This ensures data security and confidentiality.

### Phase 5: Adding Monitoring (TBD)

Implement monitoring mechanisms to keep track of the solution's health and performance.

## Conclusion

This documentation outlines a comprehensive approach to utilizing AWS S3, AWS Cognito, and AWS KMS for secure storage, authentication, and data encryption. Following these steps will help you build a robust and secure solution for your application's data management needs.

### Create  Key

1. **Create Symmetric Key**

   * Command

   ```bash
   aws kms create-key
   ```

   * Result, also `

   ```bash
   {
       "KeyMetadata": {
           "Origin": "AWS_KMS",
           "KeyId": "e84dcd58-0e4c-44a2-99d2-2155abc8cee3",
           "Description": "",
           "KeyManager": "CUSTOMER",
           "Enabled": true,
           "KeyUsage": "ENCRYPT_DECRYPT",
           "KeyState": "Enabled",
           "CreationDate": 1590485504.179,
           "Arn": "arn:aws:kms:ap-southeast-1:494526681395:key/e84dcd58-0e4c-44a2-99d2-2155abc8cee3",
           "AWSAccountId": "494526681395"
       }
   }
   ```

2. **Default policy that `CreateKey` and console applies are different**

   * Command

   ```bash
   aws kms get-key-policy --key-id e84dcd58-0e4c-44a2-99d2-2155abc8cee3 --policy-name default --output text
   aws kms get-key-policy --key-id e08d0a49-8340-4f12-b85d-8c097ad3883a --policy-name default --output text
   ```

   * Result

   ```bash
   {
     "Version" : "2012-10-17",
     "Id" : "key-default-1",
     "Statement" : [ {
       "Sid" : "Enable IAM User Permissions",
       "Effect" : "Allow",
       "Principal" : {
         "AWS" : "arn:aws:iam::494526681395:root"
       },
       "Action" : "kms:*",
       "Resource" : "*"
     } ]
   }
   {
     "Version" : "2012-10-17",
     "Id" : "key-consolepolicy-3",
     "Statement" : [ {
       "Sid" : "Enable IAM User Permissions",
       "Effect" : "Allow",
       "Principal" : {
         "AWS" : "arn:aws:iam::494526681395:root"
       },
       "Action" : "kms:*",
       "Resource" : "*"
     } ]
   }
   ```



### Encrypt data

1. Command

```bash
aws kms encrypt --key-id e84dcd58-0e4c-44a2-99d2-2155abc8cee3 --plaintext file://config-plaintext.json --output text --query CiphertextBlob | base64 --decode > config-encrypted.json
```


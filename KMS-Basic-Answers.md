### 1. What is KMS ?

AWS Key Management Service (AWS KMS) is a managed service that makes it easy for you to create and control *customer master keys* (CMKs), the encryption keys used to encrypt your data.



### 2. KMS can handle which problems? 
*能解决什么问题？使用场景？*

1. Use AWS KMS to create and manage master keys (CMKs). You can establish policies that determine who can use your CMKs and how they can use them. You can track their use in transaction and audit logs, such as [AWS CloudTrail](https://docs.aws.amazon.com/kms/latest/developerguide/logging-using-cloudtrail.html).
2. You can use your CMKs to encrypt small amounts of data (up to 4096 bytes). However, CMKs are typically used to generate, encrypt, and decrypt the [data keys](https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#data-keys) that encrypt your data. Unlike CMKs, data keys can encrypt data of any size and format, including streamed data.



### 3. The approaches to use KMS.
*KMS的使用方式？(四种)*

* AWS Command Line 
* Web Console
* APIs
* SDKs



### 4. You can do which action by using KMS(you should know at least 5 or more)?

*列出主要的操作，以了解可以怎样使用KMS*

1. Basic management actions:
   - [Create](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html), and [view](https://docs.aws.amazon.com/kms/latest/developerguide/viewing-keys.html) [symmetric and asymmetric CMKs](https://docs.aws.amazon.com/kms/latest/developerguide/symmetric-asymmetric.html), and [edit](https://docs.aws.amazon.com/kms/latest/developerguide/editing-keys.html) their properties.
   - [Enable and disable](https://docs.aws.amazon.com/kms/latest/developerguide/enabling-keys.html) CMKs
   - Create and view [access control policies](https://docs.aws.amazon.com/kms/latest/developerguide/control-access.html) and [grants](https://docs.aws.amazon.com/kms/latest/developerguide/grants.html) for your CMKs
   - Enable and disable [automatic rotation](https://docs.aws.amazon.com/kms/latest/developerguide/rotate-keys.html) of the cryptographic material in a CMK
   - [Tag your CMKs](https://docs.aws.amazon.com/kms/latest/developerguide/tagging-keys.html) for easier identification, categorizing, and tracking use and costs
   - [Create, delete, list, and update aliases](https://docs.aws.amazon.com/kms/latest/developerguide/programming-aliases.html), which are friendly names for your CMKs
   - [Delete CMKs](https://docs.aws.amazon.com/kms/latest/developerguide/deleting-keys.html) to complete the key lifecycle
2. Cryptographic operations
   - Encrypt, decrypt, and re-encrypt data with symmetric or asymmetric CMKs
   - Sign and verify messages with asymmetric CMKs
   - Generate exportable symmetric data keys and asymmetric data key pairs
   - Generate random numbers suitable for cryptographic applications
3. Advanced features
   - [Import cryptographic material](https://docs.aws.amazon.com/kms/latest/developerguide/importing-keys.html) into a CMK
   - Create CMKs in your own [custom key store](https://docs.aws.amazon.com/kms/latest/developerguide/custom-key-store-overview.html) backed by a AWS CloudHSM cluster.
   - Connect directly to AWS KMS through a [private endpoint in your VPC](https://docs.aws.amazon.com/kms/latest/developerguide/kms-vpc-endpoint.html)
   - Use [hybrid post-quantum TLS](https://docs.aws.amazon.com/kms/latest/developerguide/pqtls.html) to provide forward-looking encryption in transit for the data that you send AWS KMS






# AWS 
## Secure Architectures

####Security, Identity, and Compliance

#####1. AWS Identity and Access Management (IAM) ![IAM](icon/Resource-Icons_07312022/Res_Security-Identity-and-Compliance/Res_48_Light/Res_AWS-Identity-Access-Management_AWS-STS_48_Light.png)

![iam-how-it-works](icon/Secure/iam-how-it-works-diagram.04a2c4e4a1e8848155840676fa97ff2146d19012.png)


#####Features


- Authentication
- Authorization
- Global service (regardless regions)
- First IAM users has no any permission.
- Can attach multiple policy for user.

#####AWS root user
- First created user
- Highest permission
- Root account credentials

#####Components

- **User**
	- who can access AWS resources by using **username-password** or (**access key** and **secret key**)
	- be created by root user

- **Access key**
	- string is **20** characters long.
- Secret key
	- string is **40** characters long.	 

=> Access key and Secret key were used to initial API, SDK and authenticate CLI.

- **Password policy**
	- Definition of rules to validate password such as length, complexity, e.g . period
- **Multi-Factor Authentication (MFA)**
	- Secure account
	- **6** characters
	- For Root user 
- **Group**
	- 1 collection of IAM users	 
- **Role**
	- Manage IAM which can access AWS resources 
- **Policy**
	- JSON 
	- Always go with Group, Roles, User 

#####AWS CLI

- Command line interface that help access to AWS service.

#####2. AWS Key Management Service (AWS KMS) 


#####4. AWS Identity and Access Management (IAM) 

#####5. AWS Key Management Service (AWS KMS) 





## Authors

- [daiking](https://github.com/mrdaiking)




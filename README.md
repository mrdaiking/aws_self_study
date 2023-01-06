# Secure Architectures

## I. Security, Identity, and Compliance

### 1. AWS Identity and Access Management (IAM) ![IAM](icon/Resource-Icons_07312022/Res_Security-Identity-and-Compliance/Res_48_Light/Res_AWS-Identity-Access-Management_AWS-STS_48_Light.png)

![iam-how-it-works](icon/Secure/iam-how-it-works-diagram.04a2c4e4a1e8848155840676fa97ff2146d19012.png)

#### Features

- Authentication
- Authorization
- Global service (regardless regions)
- First IAM users has no any permission.
- Can attach multiple policy for user.

#### Use cases

- Apply fine-grained permissions and scale with attribute-based access control
- Manage per-account access or scale access across AWS accounts and applications
- Establish organization-wide and preventative guardrails on AWS
- Set, verify, and right-size permissions toward least privilege

#### AWS root user

- First created user
- Highest permission
- Root account credentials

#### Components

- **User**

  - who can access AWS resources by using **username-password** or (**access key** and **secret key**)
  - be created by root user

- **Access key**
  - string is **20** characters long.
- **Secret key**
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

#### AWS CLI

- Command line interface that help access to AWS service.

### 2. AWS Key Management Service (AWS KMS)

![iam-how-it-works](icon/Secure/AWS-KMS.png)

#### Features

- Create and manage keys to protect data.
- Maximum 4KB data for each calling.
- No compatible for big data.
- Enable and disable KMS keys and automatic rotation.
- Delete to complete the key
- Create multi-Region keys

#### KMS - Customer Master Key 　(CMK) Types

- _Symmetric_ (AES - 256 keys)
  - Single encryption ( en & de)
- _Asymmetric_ (RSA & ECC key pairs)
  - Public and Private key pairs
  - En & De or Sign/Verify
  - Private key can be download, but private key need to keep carefully.

#### KMS Automatic Key Rotation

- Used for Customer-managed CMK
- After a period time, key will be expire, need to require renewal key
- Annual or manually renewal after 90 days, 180 days

### 3. AWS CloudHSM (Cloud Hardware Security Module)

![Cloud HSM](icon/Secure/AWS-CloudHSM.png)

#### Features

- Manage and acess keys on FIPS-validated hardware, protected with customer-owned, single-tenant HSM
- Suitable with SSE-C encryption

#### Use cases

- Encrypt data at rest
- Offload SSL processing for web servers
- Protect private keys for an issuing CA
- Activate TDE for Oracle databases

### 4. AWS Shield

![Shield](icon/Secure/AWS%20Shield.png)

#### Features

- Standard
  - Static threshold DDoS protection for underlying AWS services
  - Inline attack mitigation
  - Free
- Advanced
  - _Tailored_ detection based on application traffic patterns
  - Health-based detection
  - Advanced attack mitigation
  - Automatic application layer DDoS mitigation
  - Option $3 per month
  - Determine over Health-check
  - Support 24/24

### 5. AWS WAF

![](icon/Secure/AWS-WAF.png)

#### Features

- Web traffic filtering
  - IP addresses, HTTP headers and body, or custom URIs.
  - Multiple websites with single set of rules.
- AWS WAF Bot Control
  - Detect scrapers, scanners, and crawlers
- Account takeover fraud prevention
- Against automated login attempts by bots.
- Full feature API
  - Deloy and provisioned automatically with **AWS CloudFormation**
- Real-time visibility
  - Integrated with **Amazon CloudWatch**
- Deploy on **Application Load Balancer**, **API Gateway**, **CloudFront**
- Integration with **AWS Firewall Manager**

#### Use cases

- Filter web traffic
- Prevent account takeover fraud
- Administer AWS WAF with APIs

### 6. AWS GuardDuty

![](icon/Secure/AWS-GuardDuty.png)

#### Features
- Accurate, account-level threat detection
- Continous monitoring across AWS accounts without added cost and complexity
	- **AWS CloudTrail**, **VPC Flow Logs**, and **DNS Logs**
- Threat detections developed and optimized for the cloud
	- Reconnaissance
	- Instance compromise
	- Account compromise
	- Bucket compromise
- Threat severity levels for efficient prioritization
- Threat response and remediation automation 
- Highly available threat detection
- One-click deployment with no addtional software or infrastruture to deploy and manage

#### Use cases

- Improve security operations visibility
- Assist security analyst in investigations
- Identify files containing malware
- Route insightful information on security findings


### 7. Amazon Inspector
![](icon/Secure/Amazon-Inspector.png)

#### Features
- _Vulnerability_ management for compute workloads
- Simplified one-click onboarding and integration with **AWS Organizations**
- Automated discovery and continual vulnerability scanning
- AWS Systems Manager Agent
- Inspector risk score for findings
- Suppression of findings
- Automatic closure of _remediated_ findings
- Detailed coverage monitoring
- Integration with Security Hub and EventBridge
- Vulnerability mapping to layers in Lamda functions

#### Use cases
- Quickly discover vulnerabilities in compute workloads
- Prioritize patch remediation
- Meet compliance requirements
- Identify zero-day vulnerabilities sooner

### 8. AWS CloudTrail

![](icon/Secure/AWS-CloudTrail.png)

#### Features
- Always on 
- Storage and monitoring
- _Immutable_ and encrypted activity logs
- _Insights_ and analytics
- Multi-region
- Multi-account

#### Use cases
- Audit activity
- Identify security incidents
- Troubleshoot operational issues

### 9. AWS CloudWatch
![](icon/Secure/Amazon-CloudWatch.png)

#### Features
- Collect
	- Easily collect and store logs
		- Vended logs
		- Logs published by AWS services
		- Custom logs 
	- Collect and _aggregate_ infrastructure and application metrics
	- Collect and aggregate container metrics and logs
	- Collect and aggregate Lamda metrics and logs
	- Stream Metrics
- Monitor
	- Cross-account observability across multiple AWS accounts
	- Unified operational view with dashboard
	- _Composite_ alarms
	- High-resolution alarms
	- Logs and metrics _correlation_ 	
	- Application Insights
	- Container monitoring insights
	- Internet Monitor
	- Lamda monitoring insights
	- _Anomaly_ Detection
	- ServiceLens
	- Synthetics
	- RUM
- Act
	- Auto Scaling
	- Automate repsonse to operational changes with CloudWatch Events
	- Alarm and automate actions on EKS, ECS, and k8s clusters
- Analyze
	- Granular data and extended retention
	- Custom operations on metric
	- Log analytics
	- Analyze container metric, logs, and traces
	- Analyze Lambda metrics, logs, and traces
	- Contributor Insights
	- Metrics Insights
	- Evidently
- Compliance and Security

#### Use cases
- Monitor application performance
- Perform root cause analysis
- Optimize resources proactively
- Test website impacts

#### Components
- CloudWatch Metric 
	- Provide metric for all AWS services
	- Metric: CPU, NetworkIn, NetworkOut...
	- Dimensions: key/value
	- **Maximum 10** dimensions / metric
	- Require link to timestamp
	- To create using PutMetricData
- CloudWatch Logs
	- Log groups
	- Log stream
	- Determine (Forever, 30 days..)
- CloudWatch Logs Metric Filter & Insights
	- Filter data
	- Simply query logs
- CloudWatch Agent
	- By default EC2 cannot send log to CloudWatch
	- **Require** run CloudWatch Agent on EC2 to push log 
- CloudWatch Alarms 
	- Trigger notification for metric
	- Options: min, max, %, sampling
	- Alarm states: OK, INSUFFICIENT_DATA, ALARM
	- Period
- EC2 Instance Recovery
	- StatusCheckFailed_System metric
	- Recovery an EC2 without changing Private/Public IP, Elastic IP, metadata...

### 10. AWS Config


![](icon/Secure/Amazon-CloudWatch.png)



#### Use cases

- Streamline operational troubleshooting and change management
- Deploy a compliance-as-code framework
- Continually audit security monitoring and analysis


## Authors

- [daiking](https://github.com/mrdaiking)

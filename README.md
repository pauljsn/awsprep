# awsprep
### AWS Concepts &amp; Exam prep

https://start.jcolemorrison.com/aws-vpc-core-concepts-analogy-guide/#aws-account

### VPC & Networking: 
https://start.jcolemorrison.com/aws-vpc-core-concepts-analogy-guide/#aws-account

AWS Solution Architect Associate Exam Study Notes: VPC (Virtual Private Cloud): https://www.mattbutton.com/2017/10/10/aws-solution-architect-associate-exam-study-notes-vpc-virtual-private-cloud/



**Entry Point**: console.aws.amazon.com

#### Services Layer - Account & Services
* When you login to AWS using your email, that becomes the root account.
* Use IAM APIs to create less privileged users under your root account.
* Direct Connect to connect directly to AWS Infrastructure without the internet.
* All actions done in the web-console (online) are API calls.
* All commands executed by CLI are API calls and require API key configuration
* All commands from SDKs are API calls, require API key configuration. SDKs automatically perform request signing.

### AWS Routing ###
https://medium.com/@mda590/aws-routing-101-67879d23014d

AWS makes routing simple by abstracting the complex configuration required when configuring hardware routers, and only requiring users of the platform to manage simple routing tables with a few fields. AWS’ underlying infrastructure handles the rest. That being said, there are still several different options for routing which need to be considered and then configured, based on the size and complexity of your AWS environment.



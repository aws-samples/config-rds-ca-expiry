## Detect RDS instances with expiring CA certificates

Following security best practices, it is recommended to [encrypt data in-transit between application servers and relational databases](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/UsingWithRDS.SSL.html). Secure Socket Layer (SSL) or Transport Layer Security (TLS) connections can perform server identity verification by validating the server certificate installed on the database instances. Database certificate authenticity verification is achieved by signing them with a Certificate Authority (CA) that has its own expiration dates.

Although the [Amazon RDS and Aurora](https://docs.aws.amazon.com/rds/) console notifies customers about instances requiring certificate updates, customers must log into each AWS account and navigate to relevant page in each region. This task becomes more complex when customers need to assess certificate validity across numerous AWS accounts managed by [AWS Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_introduction.html). This pattern provisions an AWS Config rule, AWS Lambda function, along with necessary permissions. It can be deployed either into a single account as an [AWS CloudFormation](https://docs.aws.amazon.com/cloudformation/) Stack or across the entire AWS Organization as an AWS CloudFormation [StackSet](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-cloudformation-stackset.html).

## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.


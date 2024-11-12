# Cloud Custodian EC2 EBS Audit

<p align="center">
  <img src="https://cloudcustodian.io/img/logo_capone_devex_cloud_custodian.svg" alt="Cloud Custodian Logo" width="200px" height="200px" />
</p>

This project uses **Cloud Custodian (c7n)** to perform audits on AWS EC2 instances, specifically focusing on EBS volumes attached to EC2 instances. The audit checks for the encryption status of the attached EBS volumes and ensures that EC2 instances are compliant with security and encryption best practices.

## Features

- Audit AWS EC2 instances and their associated EBS volumes.
- Identify EC2 instances that have unencrypted EBS volumes.
- Automatically take action (e.g., terminate instances) based on policy compliance.

## Requirements

- **AWS CLI**: Make sure you have the AWS CLI installed and configured with the necessary credentials.
- **Python 3.x**: Cloud Custodian requires Python 3.x for installation and operation.
- **Cloud Custodian (c7n)**: This project utilizes Cloud Custodian for auditing.

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/SudevShibu/cloud-custodian-ec2-ebs-audit.git
   cd cloud-custodian-ec2-ebs-audit
2. Set up a virtual environment:

python3 -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`

3. Install the required dependencies:
   pip install -r requirements.txt

4. Install Cloud Custodian:
   pip install c7n

Usage

1. Create your Cloud Custodian policy in YAML format. For example:
   
   policies:
  - name: ec2-ebs-encryption
    description: |
      Checks EC2 instances for unencrypted EBS volumes.
    resource: aws.ec2
    filters:
      - type: ebs
        key: Encrypted
        value: false
    actions:
      - terminate

2. Validate the policy:
   custodian validate policy.yml

3. Run the policy:
   custodian run -s out policy.yml
   Cloud Provider Supported
AWS: This project currently supports auditing EC2 instances in AWS.
Contributing
We welcome contributions to improve this project. Please follow these steps:

Fork the repository.
Create a new branch for your changes.
Commit your changes.
Push your changes to your fork.
Open a pull request.
License
This project is licensed under the Apache 2.0 License.

Acknowledgements
Cloud Custodian for the powerful cloud resource management tool.
AWS for providing the cloud infrastructure.
markdown


### Key Sections:

- **Project Name and Description**: Gives a brief description of what your project does.
- **Features**: Key functionality of your project.
- **Requirements**: Tools or libraries needed to run the project.
- **Installation**: Steps for setting up the environment and dependencies.
- **Usage**: Instructions for creating policies and running them.
- **Cloud Provider Support**: Specifies the cloud services supported by the project.
- **Contributing**: Guidelines on how to contribute to the project.
- **License**: Details about the project’s license.

Let me know if you'd like to adjust any of the sections or add additional details!




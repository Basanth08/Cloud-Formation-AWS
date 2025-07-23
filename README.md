# Cloud-Formation-AWS

Welcome! This is my personal journey through AWS CloudFormation. Here, I created and explored various templates to learn and implement AWS infrastructure concepts, and I even set up a sample CI/CD project. Let me walk you through what I built in each folder:

## basics/
This is where I experimented with the fundamentals of CloudFormation:

- **exercise1/first-example.yaml**: I created my very first minimal EC2 instance using CloudFormation.
- **exercise2/functions.yaml**: I added tags to my EC2 instance using the `!Join` function to see how dynamic values work.
- **exercise3/update-example.yaml**: I played with updating resources by changing tags on my EC2 instance.
- **exercise4/change-set.yml**: I explored change sets by modifying the instance type and tags, learning how CloudFormation handles updates.
- **exercise5/Ref-function.yaml**: I used the `!Ref` function to reference the AWS region dynamically in my resource tags.
- **exercise6/multiResource.yaml**: I set up multiple resources—an EC2 instance and a Security Group—to understand resource relationships.
- **exercise7/MappingAndPseudo.yaml**: I experimented with mappings and pseudo parameters to select AMIs based on region.
- **exercise8/InputParameters.yaml**: I introduced parameters for things like instance type and key name, making my templates more flexible.
- **exercise9/PrintOutputs.yaml**: I learned how to print outputs from my stack, such as the public DNS of an instance.
- **exercise10/init.yaml**: I dove into advanced features like `AWS::CloudFormation::Init`, creating files and managing services for a web server.

## cicd-project/
Here, I built a sample CI/CD stack using nested CloudFormation templates:

- **cicdtemp.yaml**: I orchestrated the creation of all my CI/CD resources using nested stacks.
- **stack-template/**: I broke down the CI/CD setup into individual stack templates:
  - **app01qa.yaml**: I provisioned an application server (EC2) with Tomcat and all the necessary setup.
  - **cicds3role.yaml**: I created an IAM role and instance profile for S3 access.
  - **db01qa.yaml**: I set up a database server (EC2) with MariaDB, Memcached, RabbitMQ, and restored a database dump.
  - **jenk.yaml**: I installed and configured a Jenkins server (EC2), including importing jobs from S3.
  - **nexus.yaml**: I deployed a Nexus repository server (EC2), set up as a systemd service, and imported data from S3.
  - **sonar.yaml**: I configured a SonarQube server (EC2) with PostgreSQL and all the necessary system tweaks.
  - **wintest.yaml**: I spun up a Windows test server (EC2) with Chocolatey and Jenkins integration.

---

Every template here is something I built to learn, experiment, and demonstrate a specific AWS or DevOps concept. Feel free to use these as references or as a starting point for your own CloudFormation adventures!
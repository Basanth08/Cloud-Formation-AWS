# ☁️ Cloud-Formation-AWS

---

## 📚 Table of Contents
1. [My Learning Approach](#my-learning-approach)
2. [Basics: CloudFormation Exercises](#basics-cloudformation-exercises)
3. [CI/CD Project](#cicd-project)
4. [Final Thoughts](#final-thoughts)

---

## 🚀 My Learning Approach
I’m not just reading about AWS CloudFormation—I’m actually using it! For every template in this repository, I:
- Designed and wrote the YAML myself
- Deployed and tested it using AWS CloudFormation
- Tweaked and improved each template based on real results

This hands-on, iterative approach has helped me truly understand how each AWS resource and feature works in practice, from launching a single EC2 instance to orchestrating a full CI/CD pipeline.

---

## 🛠️ Basics: CloudFormation Exercises
This section is where I got my hands dirty with the fundamentals of CloudFormation. Each exercise builds on the last, introducing new concepts and features:

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

---

## ❗ Problem
- High cost in maintaining servers with storage
- Backup through AMI increases storage cost
- Manual setup is time-consuming
- Chances of human error

---

## 💡 Solution
- CloudFormation is the ideal tool to automate AWS stacks
- Automatic setup (NO human errors)
- Maintains state of infrastructure
- Version control (IaC)
- Repeatable and reusable

---

## 🛠️ Technologies
- **AWS CloudFormation**: Configuration management for AWS infrastructure
- **AWS Cloud Platform**: Complete infrastructure setup and maintenance

---

## 🔁 Flow of Execution
1. Check CI/CD data on S3 bucket.
2. Note down bucket name and filenames.
3. Create an S3 bucket to upload templates; create a folder named `stack-template`.
4. Note down the bucket name and folder name.
5. Create a key pair.
6. Write the root template named `cicdtemp.yaml`.
7. Write all child templates:
    - `cicds3role.yaml`
    - `jenk.yaml`
    - `nexus.yaml`
    - `sonar.yaml`
    - `wintest.yaml`
    - `app01qa.yaml`
    - `db01qa.yaml`
8. Update the root template with child template paths.
9. Upload all child templates to the S3 bucket in the `stack-template` folder.
10. Create a nested stack using `cicdtemp.yaml`.

---

## 🔄 CI/CD Project

### 📢 About Project
- CI/CD Stack Setup or Restore on AWS
- Jenkins, Nexus, SonarQube, Windows server, app & db
- Project is to help you do R&D on CI/CD
- Similar concepts in Real World Projects

After mastering the basics, I challenged myself to build a complete CI/CD stack using nested CloudFormation templates. Here’s how I broke it down:

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

## 💡 Final Thoughts
Every template in this repository is a product of my curiosity and determination to learn by doing.
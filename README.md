# BMAT Music Innovators



# App Details
.......
................................................
................................

The app consist of:

    └──

    └──

    └──

    └──

    └──


# Proposed Stack

HCL 


# Top-level directory layout

    📦bmat-devops-task
        📦docs
            ┣ 📜Back_Office DevOps_Test_v2.pdf
            ┣ 📜Back_office_architecture.png
        📦live
            ┣ 📦prod
            ┣ 📦qa
            ┣ 📦stage
        📦modules
            ┣ 📦cache
            ┣ 📦network
            ┣ 📦services
        ┣ 📜README.md


## The task can be found [here](https://github.com/adefemi171/bmat-devops-task/blob/main/docs/Back_Office%20DevOps_Test_v2.pdf)

## Infrastructure Architecture
![](docs/Back_office_architecture.png?raw=true)


## Assumptions
I assumed that the metric I will be using to scale up the number of workers is the CPUUtilization and also I assumed the threshold as the number of job in queues.

1. For cost I used t2.micro instance type and also if there are no pending job in the queue, the instance is scaled down to zero

2. For reusability I have three environment which for further use case will contain different resources based onthe environment been used.

3. For security, I am using state locking and also each environment is been isolated from the other.

## Things to still work on
1. Creating cloud watch metric and autoscaling policy
2. Hosting modules on a different repository and reaading fro there rather than reading locally
3. Set up Github Action for auto deployment

# How to setup project

### Clone the repository 

```
git clone https://github.com/adefemi171/bmat-devops-task.git
```
### Checking Out
The infrastructure is build on the ``` main ``` branch you will need to checkout to the app branch using:

```
git checkout main
```

### Change directory into either ofthe three environment

1. Create your backend for state locking can either be using S3 bucket and Dynamo DB Table or storing iit remotely on Terraform cloud

2. Create VPC

3. Create Security Group

4. Create Auto scaling group

All the above step can be done using the following command

To make sure your code is well formatted use

```
terraform fmt
```

To initialize the backend and download modules and provider from AWS and Hashicorp that is to initialize a working directory containing Terraform configuration file use

```
terraform init
```

To create an execution plan that is to check whether the execution plan for a set of changes matches your expectations without making any changes to real resources or to the state use

```
terraform plan
```

Toapply the changes required to reach the desired state of the configuration, or the pre-determined set of actions generated by the previous command use

```
terraform apply
```


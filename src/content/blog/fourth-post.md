---
title: 'Testing Locally before deploying to Production'
description: 'Using Docker, LocalStack, and Terraform'
pubDate: 'May 11 2025'
heroImage: '/blog-placeholder-2.jpg'
---

# Creating a Virtual Cloud Environment Using LocalStack and Terraform

## Merry Thanksgiving Everyone, Here's Your Present!

One thing that bothers me the most is that it isn't straightforward to practice development in AWS without incurring charges. Sure, if you want to learn or work through a set scenario, the labs are great! But how do you develop tools without risking going broke?

I was recently shown the **CloudHealth** platform, and it opened my eyes to the possibilities. The truth is—**yes**—you can develop without incurring AWS charges. There are multiple ways to emulate a cloud environment locally, saving you time and money.

With **Docker**, **LocalStack**, and **Terraform**, you can create an environment that simulates AWS services without ever touching the cloud. Let me walk you through how I do it.

---

## LocalStack and Terraform for Local AWS Emulation

**LocalStack** is a tool that emulates AWS services locally. Instead of pointing to the AWS cloud, your Terraform or application can point to an endpoint running on your own machine. For example:

```hcl
endpoints {
  s3 = "http://localhost:4566"
  # Add other services as needed
}
```

---

## You Need Three Main Tools

- **Docker:** To provide containerization.
- **LocalStack:** To emulate the AWS services locally.
- **Terraform:** Infrastructure as Code, to automate resource creation and management.

---

## Setting Up the Project

You’ll need to create a `main.tf` file for your Terraform configuration. This tells Terraform how to interact with LocalStack. Here’s a sample `main.tf` file:

### main.tf Configuration

```hcl
provider "aws" {
  access_key                  = "test"
  secret_key                  = "test"
  region                      = "us-east-1"
  s3_use_path_style           = true
  skip_credentials_validation = true
  skip_metadata_api_check     = true
  skip_requesting_account_id  = true
  endpoints {
    s3 = "http://localhost:4566"
    # Add other services as needed
  }
}
```

This configuration helps LocalStack know which AWS services to emulate and how Terraform will interact with them.

---

## Steps to Set It Up

1. **Create the `main.tf` file** as shown above.
2. Run `tflocal init` in the directory where you created the `main.tf` file. This initializes the local environment.
3. Once initialized, run `tflocal apply`. This will apply the configuration locally.

The goal is to emulate AWS services locally—like **S3**—without having to connect to the AWS cloud. Instead of pointing to the AWS service, you point it to a local endpoint on your machine.

---

## Common Setup Issues and Solutions

Make sure you set your **environment variables** correctly in the **PATH**. This ensures that Terraform and LocalStack are recognized. You may also need **Docker Desktop** installed to run LocalStack properly.

I've included links below to the official Docker and Terraform documentation pages. These should help you solve any issues that come up during setup.

---

## Useful Links

- [Docker: Accelerated Container Application Development](https://www.docker.com/)  
  A complete guide to using Docker to simplify containerized application development.
- [LocalStack Documentation](https://docs.localstack.cloud/)  
  Learn more about using LocalStack to emulate AWS services.
- [Terraform Documentation](https://registry.terraform.io/)  
  Learn how to use Terraform to automate infrastructure using Infrastructure as Code.
- [AWS Documentation for Testing Infrastructure with LocalStack](https://docs.aws.amazon.com/)  
  Guidance on using LocalStack with Terraform for AWS infrastructure testing.

---

## Final Thoughts

Setting up LocalStack with Terraform and Docker can be a bit of a process, but it’s worth the effort if you want to avoid unexpected AWS charges. It’s also a great way to learn and experiment with **Infrastructure as Code** without worrying about cost.

<!--
![Docker Setup Screenshot](assets/images/localstack1.png)
![Terraform Setup Screenshot](assets/images/localstack2.png)
![LocalStack Screenshot](assets/images/localstack3.png)
-->

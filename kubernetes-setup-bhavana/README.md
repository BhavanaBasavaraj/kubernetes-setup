Kubernetes Project - Bhavana
This project demonstrates how to set up Amazon Elastic Kubernetes Service (EKS) to deploy a sample application using Kubernetes. It covers setting up your AWS environment, configuring EKS, and deploying a sample app to the cluster.

Project Overview
In this project, you'll:

Create an AWS account and set up IAM users.
Configure the AWS CLI and kubectl.
Prepare the networking setup for EKS.
Launch an EKS cluster.
Deploy a sample Kubernetes application.

Tools Required
AWS Account
AWS CLI (Command Line Interface)
kubectl (Kubernetes command-line tool)
Docker (for building container images)

Project Structure
This project includes the following Kubernetes configuration files:

deployment.yaml – Defines the app deployment.
service.yaml – Exposes the app within the cluster.
ingress.yaml – Manages external access to the app.


Steps to Complete the Project
Step 1: Create an AWS Account and IAM User
Go to AWS and create an account.
Access the IAM service in the AWS Management Console.
Create a new IAM User with Administrator Access and Programmatic Access.
Download the Access Key ID and Secret Access Key for the user.


Step 2: Install and Configure AWS CLI and kubectl
Install AWS CLI
Download and install the AWS CLI from here.

Configure AWS CLI
Run the following command in your terminal:

aws configure
Enter your Access Key ID, Secret Access Key, region, and output format.

Install kubectl
Download and install kubectl from here.

Connect kubectl to EKS
Use the following command to update your kubeconfig for your EKS cluster:
aws eks update-kubeconfig --name your-cluster-name


Step 3: Prepare AWS Networking (VPC and Security Groups)
Create a VPC
In the AWS Management Console, go to the VPC service and create a new VPC with both public and private subnets.

Create a Security Group

Go to Security Groups in the VPC service.
Create a new Security Group and allow inbound traffic on port 22 (SSH) and 80 (HTTP).
Set Up an Internet Gateway

Create an Internet Gateway and attach it to your VPC.
Update your Route Tables to allow internet access.

 Launch an EKS Cluster
In the AWS Management Console, go to EKS and click Create Cluster.
Provide a name for your cluster and choose your VPC and subnets.
Wait for the cluster status to become Active.


Deploy a Sample Application to EKS
Apply Kubernetes Configurations
Run the following commands to deploy your app to the EKS cluster:
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
kubectl apply -f ingress.yaml

Verify the Deployment
Check the status of your pods and services:
kubectl get pods
kubectl get services
Access Your Application
Use the Ingress endpoint to access your application in a web browser.

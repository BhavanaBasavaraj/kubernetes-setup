**Kubernetes Project - Bhavana**
This project demonstrates how to set up Amazon Elastic Kubernetes Service (EKS) to deploy a sample application using Kubernetes. It covers setting up your AWS environment, configuring EKS, and deploying a sample app to the cluster.


**Project Overview**
In this project, you'll:

1.	Create an AWS account and set up IAM users.
2.	Configure the AWS CLI and kubectl.
3.	Prepare the networking setup for EKS.
4.	Launch an EKS cluster.
5.	Deploy a sample Kubernetes application.

**Tools Required**
1.	AWS Account
2.	AWS CLI (Command Line Interface)
3.	kubectl (Kubernetes command-line tool)
4.	Docker (for building container images)

**Project Structure**
This project includes the following Kubernetes configuration files:

1.	deployment.yaml – Defines the app deployment.
2.	service.yaml – Exposes the app within the cluster.
3.	ingress.yaml – Manages external access to the app.


**Steps to Complete the Project**

Step 1: 
•	Create an AWS Account and IAM User
•	Go to AWS and create an account.
•	Access the IAM service in the AWS Management Console.
•	Create a new IAM User with Administrator Access and Programmatic Access.
•	Download the Access Key ID and Secret Access Key for the user.


Step 2: 
1.	Install AWS CLI
2.	Configure AWS CLI
aws configure
Enter your Access Key ID, Secret Access Key, region, and output format.
3.	Install kubectl
4.	Connect kubectl to EKS
Use the following command to update your kubeconfig for your EKS cluster:
aws eks update-kubeconfig --name your-cluster-name


Step 3: 
1.	Create a VPC
    In the AWS Management Console, go to the VPC service and create a new VPC with both public and private subnets.
2.	Create a Security Group
    Go to Security Groups in the VPC service.
    Create a new Security Group and allow inbound traffic on port 22 (SSH) and 80 (HTTP).
3.	Set Up an Internet Gateway
    Create an Internet Gateway and attach it to your VPC.
    Update your Route Tables to allow internet access.


Step 4 : 
4.	Launch an EKS Cluster
5.	In the AWS Management Console, go to EKS and click Create Cluster.
6.	Provide a name for your cluster and choose your VPC and subnets.
7.	Wait for the cluster status to become Active.


Step 5: 
1.	Deploy a Sample Application to EKS
2.	Apply Kubernetes Configurations
Run the following commands to deploy your app to the EKS cluster:
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
kubectl apply -f ingress.yaml
3.	Verify the Deployment
Check the status of your pods and services:
kubectl get pods
kubectl get services
4.	Access Your Application
Use the Ingress endpoint to access your application in a web browser.



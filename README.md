# Captstone Project - WordPress Site on AWS

## <ins>Project Scenario</ins>
A small to medium-sized digital marketing agency, "DigitalBoost", wants to enhance its online presence by creating a high-performance WordPress-based website for their clients. The agency needs a  scalable, secure, and cost-effective solution that can handle increasing traffic and seamlessly intergrate with their exisitng infrastructure. Your task as an AWS Solutions Architect is to design and implement a WordPress solution using various AWS services such as Networking, Compute, Object Storaage and Databases.

### <ins>1.) VPC Setup</ins>
  <ins>Objective</ins>: Create a Virtual Prviate Cloud (VPC) to isolate and secure the WordPress infrastructure.
#### - <ins>Create a VPC and Define IP address range for the VPC</ins>

![Screenshot (98)](https://github.com/user-attachments/assets/f99dbe95-653b-4e72-aa0b-e3f0c6eee5b2)

![Screenshot (99)](https://github.com/user-attachments/assets/1d5251fb-5e53-4e8c-93f7-e3fc88de713f)

![Screenshot (100)](https://github.com/user-attachments/assets/ba53d7b2-fbfe-44ab-a53c-ac453c0829b9)

![Screenshot (101)](https://github.com/user-attachments/assets/3d4ce3ad-07e2-4b45-bb0b-6c21b93c870f)

####  - <ins>Create public and private subnets</ins>
  - Firstly, i link the VPC i just created to the subnets and then i created the two public subnets

![Screenshot (102)](https://github.com/user-attachments/assets/0d1d1356-756b-40a9-bdf7-9b8f012b2fc1)

![Screenshot (110)](https://github.com/user-attachments/assets/73ae002d-4ab1-48f4-b10d-b39bc7891c60)

![Screenshot (111)](https://github.com/user-attachments/assets/c7136cb0-24b3-46b8-87c8-98e3b624c08c)

  - Secondly, i created the two private subnets

![Screenshot (112)](https://github.com/user-attachments/assets/9716717f-0606-4ada-ad7e-ba5db9083f6b)

![Screenshot (113)](https://github.com/user-attachments/assets/9475fd6b-0705-4ff3-962a-9a875e09cd83)

![Screenshot (114)](https://github.com/user-attachments/assets/0dc781cc-90fd-499e-8d30-226af50d5e1c)

#### - <ins>Configure route tables for each subnet</ins>
  - Firstly, i created the route tables for the public and private subnets

<ins>Public Subnet</ins>

![Screenshot (125)](https://github.com/user-attachments/assets/c5c37911-a35c-4f1a-9b82-86b756f50786)

![Screenshot (126)](https://github.com/user-attachments/assets/931286b1-66ef-4062-917a-12fe4d9dafe8)

<ins>Private Subnet</ins>

![Screenshot (128)](https://github.com/user-attachments/assets/f3a468d8-ffdd-4122-8eaf-3248ba02f04a)

![Screenshot (130)](https://github.com/user-attachments/assets/39211ee9-1b6c-46b6-9b1d-0eda5ab11b75)

  - Secondly, I linked the route tables to the associated subnets through the subnet associations tab

<ins>Public Subnets</ins>

![Screenshot (133)](https://github.com/user-attachments/assets/09a80297-e2c3-4664-a4e4-ec9d36d5ac5b)

![Screenshot (134)](https://github.com/user-attachments/assets/6dd62b13-7bb8-4648-b8f6-a8b4322f3649)

![Screenshot (136)](https://github.com/user-attachments/assets/22a7dfac-c255-4d09-8abf-6d8501420859)

![Screenshot (137)](https://github.com/user-attachments/assets/e16b819a-2d3b-4408-92fa-390567435045)

<ins>Private Subnets</ins>






















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

![Screenshot (139)](https://github.com/user-attachments/assets/0c935d66-4b9c-4be2-ad9c-0ac42adafcad)

![Screenshot (140)](https://github.com/user-attachments/assets/2034314e-8d2c-49db-a782-37d529fe6c0e)

![Screenshot (142)](https://github.com/user-attachments/assets/d0c8f772-143a-4cd0-9f7c-8f60a4c4c353)

![Screenshot (143)](https://github.com/user-attachments/assets/b46d56cb-e338-44f7-9ff4-514a6396d5a2)

### <ins>2.) Public and Private Subnet with NAT Gateway</ins>
  <ins>Objective: Implement a secure network architecture with public and private subnets. Use a NAT Gateway for private subnet internet access</ins>
#### - <ins>Set up public subnet for resources accessible from the internet</ins>

  - Firstly, I created an internet gateway to connect to the public subnets to allow internet access into the subnets and then attached it to the VPC i created earlier

![Screenshot (116)](https://github.com/user-attachments/assets/979375fc-29d9-433d-a74b-e7753201a560)

![Screenshot (117)](https://github.com/user-attachments/assets/c8ac99b3-3ae9-46af-a317-0a88391fd4f6)

![Screenshot (118)](https://github.com/user-attachments/assets/69ea5237-8f13-4f9a-aea6-2b4cb29d0fd9)

![Screenshot (119)](https://github.com/user-attachments/assets/4365f25b-9df0-43a9-aae1-cf4a22bb772a)

  - Edit routes and add the internet gateways to the public subnets

![Screenshot (145)](https://github.com/user-attachments/assets/9250a14d-b2e3-4454-80b2-c58c062f2bfa)

Set the beginning IP range to 0.0.0.0/0

![Screenshot (146)](https://github.com/user-attachments/assets/dc84efa9-ca6e-46dd-8528-a4fafb4d25a9)

![Screenshot (147)](https://github.com/user-attachments/assets/2818f998-5b3c-4c41-ba0a-25ec85c2818e)

![Screenshot (148)](https://github.com/user-attachments/assets/c2124234-67db-40fe-9dc5-80fd72d4bb59)

![Screenshot (149)](https://github.com/user-attachments/assets/5eaba8fc-7f38-4c20-aba0-845bad4666e0)

![Screenshot (150)](https://github.com/user-attachments/assets/4cc954c5-95e1-4bb8-b930-78091a612390)

#### - <ins>Create a NAT Gateway for private subnet internet access</ins>

- While creating the NAT Gateway, i link the first and second private gateways respectively and choose the private connectivity type for both gateways

![Screenshot (121)](https://github.com/user-attachments/assets/83d2239b-8806-4a13-a834-6468798afab2)

![Screenshot (122)](https://github.com/user-attachments/assets/d6d73df0-1321-4ec0-8364-59a2a9dd62be)

![Screenshot (123)](https://github.com/user-attachments/assets/60c80d87-5feb-4ab9-856a-57c8549080ea)

![Screenshot (124)](https://github.com/user-attachments/assets/4e40635c-dbbf-41c7-b208-740929dafc24)

- After creating the Gateways, through the route table section, i added the NAT Gateway to the route list of both private subnets

![Screenshot (155)](https://github.com/user-attachments/assets/2af6417f-b854-429d-8168-167e79efb428)

![Screenshot (156)](https://github.com/user-attachments/assets/b0905d2b-ad16-486f-b498-6649315105d5)

![Screenshot (159)](https://github.com/user-attachments/assets/347eab95-f542-43a7-8428-bb515466bb6a)

![Screenshot (160)](https://github.com/user-attachments/assets/176e3c48-0b9d-4768-9ce6-dc25d5b4c115)

- I have now configured the public subnets with an internet gateway to allow for internet access into the subnet and configured a NAT Gateway with private connectivity to the private subnets to allow for offline and private access to the subnets.

### <ins>3.) AWS MySQL RDS Setup</ins>
  <ins>Objective: Deploy a managed MySQL database using Amazon RDS for WordPress data storage.</ins>
- Create an Amazon RDS instance with MySQL engine

Firstly, i search Amazon RDS on the AWS website and navigate to the create databse page

![Screenshot (162)](https://github.com/user-attachments/assets/dc779afc-3b0a-4bc5-8b60-82b9c700d82c)

On the Create page, i choose Standard Create and choose the MySQL Engine

![Screenshot (163)](https://github.com/user-attachments/assets/0c0ab301-cfd5-40e9-8bef-80b8323e8226)
![Screenshot (164)](https://github.com/user-attachments/assets/9622e35e-851c-4faa-b786-3899153ad38d)

With the latest version and a Free tier template

![Screenshot (165)](https://github.com/user-attachments/assets/4c105a74-b626-4356-bbba-c8b1a7458ebc)
![Screenshot (166)](https://github.com/user-attachments/assets/c3abd918-185f-49d6-be48-3a48d5686211)

I choose a name for the Database, username, create a password and choose an instance configuration

![Screenshot (167)](https://github.com/user-attachments/assets/9492c33a-c546-4f9a-a3ba-25755dc201ba)
![Screenshot (168)](https://github.com/user-attachments/assets/d5103c43-0f01-45c4-8956-710c377662f9)
![Screenshot (169)](https://github.com/user-attachments/assets/7b886f2f-d147-4263-8704-1b0a7e90c9e0)

- Configure security groups for RDS Instance
I link the DigitalBoost VPC and Security group and create the Database

![Screenshot (170)](https://github.com/user-attachments/assets/fdc604f4-71d0-4f04-805c-0cac98215f06)
![Screenshot (171)](https://github.com/user-attachments/assets/7813baf7-a855-4df1-a16a-4b9fba5e20fd)
![Screenshot (172)](https://github.com/user-attachments/assets/1dc03b2f-e310-430d-b7fa-c8efd17c6bab)
![Screenshot (174)](https://github.com/user-attachments/assets/04cf7299-a583-4696-80fa-e52b914504f4)

- Connect WordPress to the RDS



























































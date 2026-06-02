Build Your DB Server

AIM:

   Create a Security Group for the RDS DB Instance.
   Create a DB Subnet Group.
   Create an Amazon RDS DB Instance.
   Interact with Your Database.
   
PROBLEM STATEMENT:

The objective of this experiment is to understand how to create and manage a relational database server using Amazon Web Services Relational Database Service (RDS).
The experiment includes configuring security groups, creating a DB subnet group, launching an RDS database instance, and connecting to the database for performing operations.
This helps in understanding secure cloud-based database deployment and management.

Explain about the Experiment.

ALGORITHM:

Steps 1:Login to the AWS Management Console and open the Amazon RDS service.

Steps 2:Create a Security Group to allow database access through the required port.

Steps 3:Create a DB Subnet Group by selecting subnets from different availability zones.

Steps 4:Create an Amazon RDS DB Instance by selecting the database engine, instance type, storage, username, and password.

Steps 5:Connect to the database instance using a database client and perform database operat

COMMANDS:

Include the commands used in the Experiment.

1. Create Security Group
aws ec2 create-security-group \
--group-name RDS-SG \
--description "Security group for RDS instance"
2. Authorize Inbound Rule for MySQL
aws ec2 authorize-security-group-ingress \
--group-name RDS-SG \
--protocol tcp \
--port 3306 \
--cidr 0.0.0.0/0
3. Create DB Subnet Group
aws rds create-db-subnet-group \
--db-subnet-group-name mydbsubnetgroup \
--db-subnet-group-description "My DB subnet group" \
--subnet-ids subnet-12345 subnet-67890
4. Create RDS DB Instance
aws rds create-db-instance \
--db-instance-identifier mydbinstance \
--db-instance-class db.t3.micro \
--engine mysql \
--master-username admin \
--master-user-password password123 \
--allocated-storage 20 \
--vpc-security-group-ids sg-12345678 \
--db-subnet-group-name mydbsubnetgroup
5. Connect to MySQL Database
mysql -h mydbinstance.xxxxxx.us-east-1.rds.amazonaws.com \
-u admin -p


OUTPUT:


REG NUMBER:212224040272

NAME:Reena K

Include your Screenshots Here.



RESULT

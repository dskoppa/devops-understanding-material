### Amazon EC2 (Elastic Compute Cloud):

1. **Instance Types**: A variety of instance types optimized for different use cases including compute, memory, storage, and GPU-intensive applications.

2. **Amazon Machine Images (AMIs)**: Pre-configured templates for instances that include operating systems and software packages.

3. **Elastic Block Store (EBS)**: Persistent block storage volumes that can be attached to EC2 instances to persist data beyond the life of the instance.

4. **Security Groups**: Virtual firewalls that control inbound and outbound traffic to EC2 instances.

5. **Elastic IP Addresses**: Static IPv4 addresses designed for dynamic cloud computing, allowing persistent public IP addresses for EC2 instances.

6. **Auto Scaling**: Automatically adjusts the number of EC2 instances based on demand to maintain application performance and optimize costs.

7. **Load Balancing**: Distributes incoming traffic across multiple EC2 instances to ensure high availability and fault tolerance.

8. **Placement Groups**: Logical grouping of instances within a single Availability Zone (AZ) to support low-latency and high-performance applications.

9. **Monitoring and Metrics**: Detailed monitoring of EC2 instances and systems using Amazon CloudWatch for performance metrics and logs.

10. **Integration with AWS Services**: Seamless integration with other AWS services such as S3, RDS, DynamoDB, and Lambda for data storage, databases, serverless computing, and more.

11. **Virtual Private Cloud (VPC) Integration**: Integration with AWS VPC for secure networking and isolation of EC2 instances within virtual networks.

12. **Instance Metadata**: Access to instance metadata, allowing instances to retrieve data about themselves for dynamic configuration.

13. **AWS Marketplace**: Access to a wide selection of third-party software and services that can be deployed on EC2 instances.

14. **IAM Roles**: Grant permissions to EC2 instances securely through IAM roles for access to AWS services and resources.

15. **Spot Instances**: Purchase spare EC2 capacity at reduced rates for flexible, interruptible workloads.

16. **Reserved Instances**: Reserved capacity for EC2 instances with significant cost savings over on-demand pricing for predictable workloads.

17. **Dedicated Hosts**: Physical servers dedicated to your use to help meet compliance requirements or licensing constraints.

18. **Instance Types for Machine Learning**: Instance types optimized for machine learning inference and training workloads, such as GPU instances.

19. **Instance Types for High-Performance Computing**: Instance types optimized for high-performance computing (HPC) workloads, such as compute-intensive simulations.

20. **Instance Types for Storage Optimization**: Instance types optimized for storage-intensive workloads, providing high disk throughput and low-latency access to storage.

Amazon EC2's rich feature set makes it a versatile choice for running a wide range of applications, from small-scale development environments to large-scale enterprise workloads requiring high availability, scalability, and performance in the cloud.

-------------------------------------

### Limits per AWS Region (General Limits)

The limits for creating EC2 resources can vary across AWS regions. Here are some typical limits:

- **Instances**: Varies by instance type and region. For example, you can typically launch hundreds to thousands of instances per region, depending on the instance type.
- **Elastic IP Addresses**: 5 per AWS account by default, but can be increased upon request.
- **Placement Groups**: 7 per Availability Zone (can vary).
- **Security Groups**: 500 per VPC (can vary).
- **Key Pairs**: 1000 per AWS account (can vary).
- **AMIs**: No specific limit, but practical limits may apply based on storage and account limits.
- **Instance Store Volumes**: Varies by instance type and region.
- **Elastic Network Interfaces (ENIs)**: 350 per VPC (can vary).
- **Load Balancers**:
   - There are different types of load balancers in AWS:
     - **Classic Load Balancer (CLB)**: Up to 20 load balancers per region & 50 Target Groups per region by default.
     - **Application Load Balancer (ALB)**: Default limit is 50 load balancers per region & 50 Target Groups per region by default.
     - **Network Load Balancer (NLB)**: Default limit is 50 load balancers per region & 50 Target Groups per region by default.
- **Auto Scaling**:
    - **Auto Scaling Groups**: Up to 20 Auto Scaling groups per region (can be increased).
    - **Launch Configurations**: Up to 200 launch configurations per region.
    - **Scaling Policies**: No specific limit documented, but practical limits apply based on service usage and AWS account limits.



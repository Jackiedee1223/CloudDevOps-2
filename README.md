# Re-architecture Web Application on AWS Cloud
<h2>Scenario</h2>
<p>
The objective of our Cloud DevOps Project is to re-architect and refactor our existing services for the AWS Cloud with a focus on enhancing agility, reducing operational overhead, eliminating upfront costs, and leveraging Infrastructure as Code (IaaC), Platform as a Service (PaaS), and Software as a Service (SaaS) models.

Currently, our services are spread across physical machines, virtual machines, and some existing cloud instances like EC2. This diversity involves managing a wide array of services, including databases, application layers, webservers, and network services like DNS and DHCP. To effectively handle this complexity, various teams such as Cloud Computing, Virtualization, DataCenter Operations, Monitoring, and System Administration have to collaborate, leading to operational overhead and challenges with uptime and scaling.

To address these issues, we aim to transition to a cloud setup focused on PaaS and SaaS offerings, embracing IaaC principles for flexible infrastructure, automation, and a pay-as-you-go model. Our chosen AWS services such as EC2 Instances, ELB, Autoscaling, EFS/S3, RDS, ElastiCache, ActiveMQ, Route53, and CloudFront will enable us to achieve these goals effectively.

Using AWS Elastic Beanstalk will streamline our deployment process by automatically provisioning EC2 instances and hosting applications without the need for manual management. Leveraging S3 for storing artifacts, RDS for databases, and services like ElastiCache for memcache and ActiveMQ for RabbitMQ will ensure easy scalability, rapid setup based on requirements, automated backups, and seamless operations.

Route 53 will handle DNS, CloudFront will serve as our Content Delivery Network (CDN), and Auto Scaling coupled with Elastic Load Balancing (ELB) will ensure dynamic load management and high availability. Embracing these AWS services will not only streamline our infrastructure but also optimize costs, reduce manual efforts, and improve our system's overall reliability and flexibility.

</p>

<h2>Architecture of AWS Services</h2>
 <img src="https://github.com/Jackiedee1223/image-repos/blob/main/CloudDevOps-2.png">

<h2>Flow of Execution</h2>

1.	Create Key pair for Beanstalk instance login: Generate a key pair that will be used for secure login to your Elastic Beanstalk instance.
2. Create Security Group for Amazon ElastiCache, RDS, and ActiveMQ: Define security groups to control inbound and outbound traffic for your ElastiCache, RDS, and ActiveMQ instances.	 
3.	Create RDS, Amazon ElastiCache, and Amazon ActiveMQ: Set up your relational database (RDS), caching with ElastiCache, and the message broker with ActiveMQ.
4.	Create Elastic Beanstalk Environment: Deploy and manage your application in an Elastic Beanstalk environment, allowing automatic scaling and easy application management.
5. Update SG of backend to allow traffic from Bean SG: Adjust security group rules to permit traffic from your Elastic Beanstalk security group to the backend services.	
6.	Update SG of backend to allow internal traffic: Configure security groups to enable internal communication between components.
7.	Launch EC2 instance for DB initializing: Start an EC2 instance dedicated to initializing and configuring your RDS database.
8. Login to the instance and initialize RDS DB: Access the EC2 instance to execute the necessary scripts or commands to initialize your RDS database.	
9.	Change health check on Beanstalk to login: Adjust the health check settings on Elastic Beanstalk to ensure it checks the login status or relevant indicators.
10.	Add 443 https Listener to ELB: Enhance security by configuring a secure HTTPS listener on your Elastic Load Balancer (ELB).
11. Build Artifact with Backend Information: Compile an artifact containing the necessary information for your backend services.
12. Deploy Artifact to Beanstalk: Use Elastic Beanstalk to deploy the compiled artifact, making your application available.
13. Create CDN with SSL Cert: Establish a Content Delivery Network (CDN) and configure it with an SSL certificate for enhanced performance and security.
14. Update Entry in GoDaddy DNS Zones: Update the DNS settings in your GoDaddy account to point to the newly created CDN and ensure proper domain resolution.
15. Test the URL: Conduct thorough testing to verify that your application is accessible and functioning correctly through the updated URL.




<h2>Validation & Summarization</h2>
<h4>Security Group & Key Pairs</h4>
<h4>EC2 Instances</h4>
<h4>Build and Deploy Artifacts</h4>
<h4>Load Balancer & DNS</h4>
<h4>Auto Scaling Group</h4>













<h2>Reference</h2>
<p>Learning from <b>GURUTECH NETWORKS</b> </p>

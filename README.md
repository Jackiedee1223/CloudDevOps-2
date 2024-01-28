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
 <img src="https://github.com/Jackiedee1223/CloudDevOps-2/blob/main/images/Arch.png">

<h2>Flow of Execution</h2>

<b>1.	<b>Create Key pair for Beanstalk instance login: Generate a key pair that will be used for secure login to Elastic Beanstalk instance.</b>
<p></p>
<b>2. Create Security Group for Amazon ElastiCache, RDS, and ActiveMQ: Define security groups to control inbound and outbound traffic for ElastiCache, RDS, and ActiveMQ instances.</b>	 
<p></p>
<b>3.	Create RDS, Amazon ElastiCache, and Amazon ActiveMQ: Set up relational database (RDS), caching with ElastiCache, and the message broker with ActiveMQ.</b>
<p></p>
<b>4.	Create Elastic Beanstalk Environment</b>: Deploy and manage the application in an Elastic Beanstalk environment, allowing automatic scaling and easy application management.</b>
<p></p>
<b>5. Update SG of backend to allow traffic from Bean SG: Adjust security group rules to permit traffic from Elastic Beanstalk security group to the backend services.</b>
<p></p>
<b>6.	Update SG of backend to allow internal traffic: Configure security groups to enable internal communication between components.</b>
<p></p>
<b>7.	Launch EC2 instance for DB initializing: Start an EC2 instance dedicated to initializing and configuring RDS database.</b>
<p></p>
<b>8. Login to the instance and initialize RDS DB: Access the EC2 instance to execute the necessary scripts or commands to initialize RDS database.</b>	
<p></p>
<b>9.	Change health check on Beanstalk to login: Adjust the health check settings on Elastic Beanstalk to ensure it checks the login status or relevant indicators.</b>
<p></p>
<b>10.	Add 443 https Listener to ELB: Enhance security by configuring a secure HTTPS listener on Elastic Load Balancer (ELB).</b>
<p></p>
<b>11. Build Artifact with Backend Information: Compile an artifact containing the necessary information for the backend services.</b>
<p></p>
<b>12. Deploy Artifact to Beanstalk: Use Elastic Beanstalk to deploy the compiled artifact, making the application available.</b>
<p></p>
<b>13. Create CDN with SSL Cert: Establish a Content Delivery Network (CDN) and configure it with an SSL certificate for enhanced performance and security.</b>
<p></p>
<b>14. Update Entry in GoDaddy DNS Zones: Update the DNS settings in GoDaddy account to point to the newly created CDN and ensure proper domain resolution.</b>
<p></p>
<b>15. Test the URL: Conduct thorough testing to verify that the application is accessible and functioning correctly through the updated URL.</b>
<p></p>

<h2>Reference</h2>
<p>Learning from <b>GURUTECH NETWORKS</b> </p>

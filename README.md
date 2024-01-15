# Lift & Shift Web Application on AWS Cloud
<h2>Scenario</h2>
<p>
The project is lift and shift application workload and we’re going to lift our application, the VPROFILE and shift it on AWS cloud. In this project, we are hosting and running it on AWS cloud for production and use a lift and shift strategy. 

Application services such as databases, application services such as Tomcat, LAMP Stack, DNS services and various kinds of services that powers application, and all these work in the Datacenter. So many servers running various services in local Data Centre. To manage all this, we need multiple teams working around clock. We need virtualization team for running virtualization platform, datacenter operations team for Data Centre and related operations work, monitoring team to monitor 24/7 and system administration team.

Managing all these services, servers and teams is complex. It becomes more complex if you want to scale up or scale down, which needs to be done very regularly. There's a huge cost for procuring all these resources and also regular maintenance cost. Most of the processes in this will be manual. If we have a virtualization layer on top of it, it is possible to automate those things, but it's really difficult to do it and also to maintain it. And not to mention all these things are very time consuming. Solution to all this problem is to have a cloud computing setup, so instead of running our workload in the data center, we run it on a cloud computing platform that we don't pay for the upfront cost for procuring the resource. We pay as we go. Consuming infrastructure as a service like electricity. We get flexibility, it's elastic in nature, we can scale out or scale in and really control our cost, managing infrastructure becomes easier. And most important, we can do automation, we can automate each and every step and process to avoid human errors and save our time.

In this project, EC2 instances as Virtual Machines for Tomcat, RabbitMQ, Memcache and MySQL servers. We will also using Elastic Load Balancer, which will be replacement of our engine service. Autoscaling service will automatically scale in and out in EC2 instances, which will automatically control our resources and also our cost. For storage, S3 or EFS storage as shared storage and Route 53 for a private DNS service. 

</p>

<h2>Architecture of AWS Services</h2>
 <img src="https://github.com/Jackiedee1223/image-repos/blob/main/CloudDevOps-1.png">
<p>
Users will access our website by using a URL and that URL we be pointing are told, will be point-to-endpoint. This entry will be mentioned in GoDaddy DNS. User browsers or the application will use this endpoint to connect to the load balancer by using HTTPS certificate for HTTPS encryption will he mentioned in Amazon Certificate Manager (ACM) Service. So, user will access application load balancer endpoint and load balancer will be in a security group and only allow HTTTPS traffic. The application load balancer will route the request to Tomcat instances. Apache Tomcat service will be running on some set of instances which will be managed by Auto Scaling Group. So as for high or low load, these instances capacity will be scaled out or scaled in. These EC2 instances where Tomcat is running in a separate security group and only allow traffic on port 8080 only from a load balancer. Our application needs backend servers which are MySQL, Memcache and RabbitMQ. Information of backend services or the backend server IP address will be mentioned in Route 53 private DNS zones. Tomcat instances will access back server with a name which will be mentioned in Route 53. Private DNS where the private IP address of background servers will be mentioned. These backend EC2 instances will be running MySQL, RabbitMQ and Memcache will be in a separate security group. So, the AWS resources which are in used over here are first Amazon Certificate Manager for a certificate Application Load Balancer. Set of EC2 instances for Tomcat, Memcache and RabbitMQ, three separate security groups. Amazon Route 53 for DNS Private Zones, Amazon S3 bucket to store software artifacts.
</p>

<h2>Flow of Execution</h2>

1.	Create Security groups
2.	Create Key pairs
3.	Launch instances with user data
4.	Update IP address to name mapping in Route 53
5.	Build application from source code
6.	Upload to S3 bucket
7.	Download artifact to Tomcat EC2 instance
8.	Setup ELB with HTTPS, certificate from ACM
9.	Map ELB endpoint to website name in GoDaddy DNS
10.	Build ASG for Tomcat instances.

<h2>Validation & Summarization</h2>
<h4>Security Group & Key Pairs</h4>
<h4>EC2 Instances</h4>
<h4>Build and Deploy Artifacts</h4>
<h4>Load Balancer & DNS</h4>
<h4>Auto Scaling Group</h4>













<h2>Reference</h2>
<p>Learning from <b>GURUTECH NETWORKS</b> </p>

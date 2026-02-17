# Deployment

* I want to deploy this project using AWS with best criteria and architecture I could figure out.
* Ofcourse there is much better ideas, but this is what I have managed to do.
* There is no code or configuration script for the deployment itself, except ofcourse the code of the project itself, made in *spring boot* (I didn't make it).



# Criteria 

* What criteria I have chosen to deploy my application with:
	1) High Availability & Reliability: Ensure continuous operation and data integrity.
	2) Cloud Scalability: Dynamically adapt to varying user loads and data volumes.
	3) Automated Deployment (CI/CD): Streamline development and deployment with CI/CD pipelines.
	4) Optimal Performance & Uptime: Deliver swift responses and maintain maximum system uptime.







# High-Level Architecture: Request diagram (Runtime flow)

* This is the front-end diagram, how the user gonna interact with our system.

![[request-flow.gif]]




# High-level architecture: Deployment diagram

* My intent was to use a fully managed AWS services (except github):

![[deployment-flow.gif]]


# High-Level Architecture: Monitoring

![[monitoring.png]]



# EC2 Setup

Servers are production-ready and managed automatically using Templates which also have user script.

* The point of the user script is to:
	1) Install docker
	2) Install **CodeDeploy agent** to fetch the latest image from ECR and trigger docker to work, using the yaml file, **appspec.yml**


* Each instance made has **inbound rules (traffic allowed to enter the ec2) + a user data script**:

![[template.png]]

* The user script content:
![[user_script.png]]
	


# Health checks & Monitoring

* ALB health check can check the instances availability by sending request to specific path on our service.
![[health_check.png]]

- CloudWatch metrics were used to generate data metrics for each ec2 instance. 
![[metrics_health_check.png]]




- The front-end is hosted in a separate [GitHub repository](https://github.com/AhmadAL-Quraan/HTU-Schedemy-Website-front-end) and deployed using AWS Amplify.










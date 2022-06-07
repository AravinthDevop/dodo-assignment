## Setup Auto Scalable Infrastructure

* Your task is to setup a auto scalable infrastructure for one of the fast growing products of the company. 
* You are free to automate the below steps with the tools and technologies of your choice.
* You may also add any missing requirements from the below problem statement. Please also put down your assumptions along with your solutions.

_You may choose AWS or Azure cloud for solving this problem_

* _requirements_

  - Setup VPC with 1 public and 1 private subnet

  - Add route tables for each subnet

  - choose a linux ami and setup webserver nginx using the frontend code from [this](https://github.com/feedmepos/devops-take-home-assignment/tree/main/frontend) location.

  - Setup ALB and open only port 80 and port 443. Its an SSL only implementation.

  - Create ASG (Auto scalable group) using AMI and configure scaling basis cpu or no of requests. You are free to assume thresholds per your understanding.

  - Create IAM policy that is needed
  - Setup alerts to know instances health and the overall health of the website and alert relevant business stakeholders
  - Setup alerts if the avg response time of api is more than 2 secs
  - Setup dashboard to understand the correlation between instance up scaling/down scaling alongside http status/failures

_Additional Notes_

* Feel free to reach out to us via the conveyed teams channel or email (`hr@crayondata.com`) in case of questions.
* Please submit the solution via Github or gitlab.
* Please write descriptive commit messages to facilitate better understanding of your approach.
* Bonus points for a scalable design.
* Do validate your solution before submitting.


_**Solution**_

To achieve this scenario, I will use the AWS resource listed below.

_preject design_

|resource|purpose|
|---|---|
|aws| cloud|

* aws ami creation
* aws ec2 instance key pair
* vpc
* subnet - 3
    * public subnet   - 2 ( Application loadbalancer require min two availabllity zone )
    * private -subnet - 1
    * route table     - 2
      * private subnet rt - 1
      * publict subnet rt - 1
* ec2 instance launch configuration
* autoscaling group
* alb load balancer
* securty groups


_**Process of ami creation**_

In order to consume the application in high availability mode. We need to prepare an AMI image. We can increase the number of instances dependent on the number of users or loads with help of autoscalling groups.

_preparation_

* create the instance
* set it up all the application based configuration and changes
* take it a AMI from the running instance

in future we can refer the AMI from the autoscalling groups.

![image](https://user-images.githubusercontent.com/106981219/172328135-5b2ea40a-949f-4cf8-a80d-c0d7d3621748.png)


_create the lunch configuration_

This lunch configuration must configure the freshly produced AMI images. This necessitates the use of attributes such as instance type, key pair, subnet, and security groups. 

![image](https://user-images.githubusercontent.com/106981219/172328204-2f965aff-105a-463d-8ffc-465f65f15626.png)


_autoscalling configuration_

Once the lunch configuration has been built, we must map it into the autoscale configuration. Instance should be expanded based on this configuration.

![image](https://user-images.githubusercontent.com/106981219/172328374-6b7a4cbf-023f-44a4-807d-3d050ca0277b.png)




  
  
  

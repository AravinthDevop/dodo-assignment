## Setup Auto Scalable Infrastructure

Your task is to setup a auto scalable infrastructure for one of the fast growing products of the company. 

You are free to automate the below steps with the tools and technologies of your choice.

You may also add any missing requirements from the below problem statement. Please also put down your assumptions along with your solutions.

You may choose AWS or Azure cloud for solving this problem



- Setup VPC with 1 public and 1 private subnet

- Add route tables for each subnet

- choose a linux ami and setup webserver nginx using the frontend code from [this](https://github.com/feedmepos/devops-take-home-assignment/tree/main/frontend) location.

- Setup ALB and open only port 80 and port 443. Its an SSL only implementation.

- Create ASG (Auto scalable group) using AMI and configure scaling basis cpu or no of requests. You are free to assume thresholds per your understanding.

- Create IAM policy that is needed

- Setup alerts to know instances health and the overall health of the website and alert relevant business stakeholders
- Setup alerts if the avg response time of api is more than 2 secs
- Setup dashboard to understand the correlation between instance up scaling/down scaling alongside http status/failures

  

### Additional Notes

1. Feel free to reach out to us via the conveyed teams channel or email (`hr@crayondata.com`) in case of questions.
2. Please submit the solution via Github or gitlab.
3. Please write descriptive commit messages to facilitate better understanding of your approach.
4. Bonus points for a scalable design.
5. Do validate your solution before submitting.

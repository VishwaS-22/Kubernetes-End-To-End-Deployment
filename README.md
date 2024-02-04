# Kubernetes-End-To-End-Deployment
Deployed a Game in the AWS EKS Cluster and Exposed to the outside world.


Hey Folks! Here is the steps to do the project:

1. Make sure you have all the pre-requisites which is mentioned in the pre-requisites file for doing this Project. 
2. Creat a EKS Cluster by following the EKS Creation file.
3. Create a FARGATE profile and deploy the GAME as pods by following the two commands mentioned in 2048 Game as Pods file.
4. Follow the commands in OIDC_and_ALB file for creating OIDC connetion and installing ALB controller.
5. Finally, you can verify it to get the external IP and access the application from any browser.

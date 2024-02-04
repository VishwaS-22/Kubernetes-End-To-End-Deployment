1. Create a Fargate profile first after created a EKS Cluster in AWS. Follow the below command:

$ eksctl create fargateprofile \
    --cluster <cluster_name> \
    --region <specify_region> \
    --name <provide_name_for_profile> \
    --namespace <provide_name_for_namespace>

2. Deploy the Deployment, Service and Ingress by running the below command:

$ kubectl apply -f https://raw.githubusercontent.com/kubernetes-sigs/aws-load-balancer-controller/v2.5.4/docs/examples/2048/2048_full.yaml

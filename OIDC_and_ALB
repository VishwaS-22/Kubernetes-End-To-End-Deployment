1. After deployment run the below command for IAM OpenID Connection:

$ eksctl utils associate-iam-oidc-provider --cluster <cluster_name> --approve

2. SetUp Application Load Balancer:

- Download the IAM Policy and Create it using the downloaded JSON code:

$ curl -O https://raw.githubusercontent.com/kubernetes-sigs/aws-load-balancer-controller/v2.5.4/docs/install/iam_policy.json

$ aws iam create-policy \
    --policy-name AWSLoadBalancerControllerIAMPolicy \
    --policy-document file://iam_policy.json

3. Create an IAM role for serviceaccount:

$ eksctl create iamserviceaccount \
  --cluster=<cluster_name> \
  --namespace=kube-system \
  --name=aws-load-balancer-controller \
  --role-name AmazonEKSLoadBalancerControllerRole \
  --attach-policy-arn=arn:aws:iam::<YOUR_AWS_ACCOUNT_ID>:policy/AWSLoadBalancerControllerIAMPolicy \
  --approve

4. Deploy the ALB Controller:

- Add helm repo and update it:

$ helm repo add eks https://aws.github.io/eks-charts

$ helm repo update eks

- Insatll the ALB:

$ helm install aws-load-balancer-controller eks/aws-load-balancer-controller \            
  -n kube-system \
  --set clusterName=<cluster_name> \
  --set serviceAccount.create=false \
  --set serviceAccount.name=aws-load-balancer-controller \
  --set region=<specify_region> \
  --set vpcId=<YOUR-VPC-ID>


5. Finally, Verify the Deployment are running using the below command:

$ kubectl get deployment -n kube-system aws-load-balancer-controller


Kudos Folks, Now you can use the External IP to access the running application through the Browser.

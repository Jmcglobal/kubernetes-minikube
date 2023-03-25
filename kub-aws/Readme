## Creating EKS Cluster using console
First you must create a role, to allow EKS to create some other resources on your behalf.

## Create EKS Cluster Role
- On your aws console search for IAM service
- Click on role to create a role
- click on create a role
- under trusted entity type, select AWS service,
    - under Use case, search and click on EKS and select "EKS-Cluster".
- click next on the bottom, under add permission, by default EKS-Cluster role have a predefined permissions/policy available, click on next again
- Under Name, Review and Create, enter name of the role, and optionally add tags and click create.

- Then use the role and create EKS cluster.

## To run command from your local machine inside the EKS cluster, update your kubectl config file with this command.

- You must create a user account and assign the appropraite permission for access or simply use admin account if you are the admin.
- create an access-key for the user account and use it to authenticate API call..
- use aws configure to enter the aceess-key details....
- aws eks update-kubeconfig --name eks-cluster --region us-east-2 
    - eks-cluster will be your own cluster name 
    - us-east will be your own region where you deployed the cluster.

## Adding a node group

Once your cluster is active, you must add some node group
- click on your cluster name, and on compute click to add node group

## Create a role for Node Group
- Inside IAM service, click on create a role
- Select AWS Service under Select tructed entity
- Under use case select EC2, click next
- under Add permission, 
## Search and select the following policy
- AmazonEKSWorkerNodePolicy
- AmazonEKS_CNI_Policy
- AmazonEC2ContainerRegistryReadOnly

Click next, under review name your role and click create.

You can now use to create your node resources inside EKS cluster.

## Using EFS Volume for Storage.

- ## inside your cluster, you must deploy a stable aws-efs-csi driver.
- ## Command:

- kubectl apply -k "github.com/kubernetes-sigs/aws-efs-csi-driver/deploy/kubernetes/overlays/stable/?ref=release-1.5"

Create EFS storage resource with appropraite parameters and reference it on kubernetes volume yaml file.

# Kubernetes Yaml file contains:
- Persistent Volume Configuration
- StorageClass Configuration
- Persistent Volume Claim Configuration
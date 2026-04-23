# NKP CI/CD Demo with Helm

The following demonstrates how to use NKP Projects Continuous Deployment (CD) to deploy a Helm chart to a Kubernetes cluster.


## Prerequisites

1. On the K8s cluster find the 'kommander-traefik' LoadBalancer IP address by running the following command:
```
kubectl get svc -A | grep kommander-traefik
```
2. Update 'nkp-demo/release.yaml' with the IP address of the LoadBalancer. Example: host: "cicd-demo-helm.10.2.0.72.nip.io" to host: "demo-app-helm.10.2.0.151.nip.io"

3. In 'nkp-demo/release.yaml' update all entries 'demo-app-helm' to a unique name for your project.


## Create Project 

Create a new Project in the NKP UI with the following settings:
- Name: 'your project name'
- Namespace: 'your project name'
- Manually Select Cluster, and select the cluster you want to deploy to


## Settings in the NKP Project Continuous Delivery (CD) GitOps Source 

GitOps Source Settings: 
- Name: 'your project name'
- Repository URL: https://github.com/pauldjmetsi/nkp-ci-cd-demo-helm
- Branch: main
- Path: ./

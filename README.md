# DevOps Internship Assignment - AI Planet
## Overview
Hello! My name is Ankush Singh and this repo is specifically made for the DevOps Internship Assignment by AI Planet.

This repo contains the kubernetes and Argo manifestaions, including ArgoCD Application file and Argo Rollouts YAML file. Up next is the step-by-step walkthrough of how I implemented the GitOps deployment pipeline using ArgoCD and Argo Rollouts for advance deployment strategies, namely Canary release.



## Tasks to be Performed
- ### Task 1
  - Create a GitRepository: Create a Github repository and host your source code in the same repository.
  - Install Argo CD on Your Kubernetes Cluster: Follow the official Argo CD documentation to install and set up Argo CD.
  - Install Argo Rollouts: Install the Argo Rollouts controller in your Kubernetes cluster, following the official guide.
- ### Task 2
  - Dockerize the Application: Build a Docker image for the web application of your choice and push it to a public container registry of your choice.
  - Deploy the Application Using Argo CD:
  - Modify the Kubernetes manifests in your forked repository to use the Docker image you pushed.
  - Set up Argo CD to monitor your repository and automatically deploy changes to your Kubernetes cluster.
- ### Task 3
  - Define a Rollout Strategy: Modify the application's deployment to use Argo Rollouts, specifying a canary release strategy in the rollout definition.
  - Trigger a Rollout: Make a change to the application, update the Docker image, push the new version to your registry, and update the rollout definition to use this new image.
  - Monitor the Rollout: Use Argo Rollouts to monitor the deployment of the new version, ensuring the canary release successfully completes.
- ### Task 4
  - Document the Process: Write a summary of the steps you took, including any challenges you encountered and how you resolved them.
  - Clean Up: Describe how to cleanly remove all resources created during this assignment from the Kubernetes cluster.

# Task 1
The project involves setting up a GitOps pipeline to automate the deployment and management of a simple web application. utilizing Argo CD for continuous deployment and Argo Rollouts for advanced deployment strategies within a Kubernetes environment.
and
We are going to do the whol Project using VM's and GitOPs Concepts

### Creating an EC2 instance in AWS Console and Installing Dependencies
Specification
- Image: Ubuntu 22.04
- Type: t2,large (We are going to run Argocd, Argo rollout, Docker and Minikube on it)
- Create a key pair
- Storage: 25 GB
- Install Docker and Minikube.
- Install ArdoCD
  ```
  kubectl create namespace argocd
  kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
  ```
  It will Create a namespace -> argocd
  and install dependencies for argocd
  ### Retrieving Password
  ```
  kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d

  username: admin
  password: will be retrived from above code
  ```
  ### Tunneling Route
  ```
  kubectl port-forward svc/argocd-server -n argocd --address 0.0.0.0 8080:443
  ```
  Now, we can access the ArgoCD via <InstanceIP>:8080

- Install ArgoRollout
  ```
  kubectl create namespace argo-rollouts
  kubectl apply -n argo-rollouts -f https://github.com/argoproj/argo-rollouts/releases/latest/download/install.yaml
  ```
  It will Create a namespace -> argo-rollouts
  and install dependencies for argocd

## Setting Up GITLAB or GITHUB
For this project we are using GitLab for following purpose:
- For storing code (Use as repository)
- For Making CICD Pipeline (or we can say perticularly CI pipeline, CD we will do with ArgCD)
  we can aslo use the jenkins for the same purpose, but I thougth as it is a gitops project so why not use git tools as much as we can.
- As Image registry.

### Steps
- Make two repository
  - [AIP_code_Repo](https://github.com/aankusshh/AI_planet_Devops/tree/main/AIP_code_Repo) (For Storing the application related code, making CI Pipeline and storing Dockerfile )
  - [API_manifest_repo](https://github.com/aankusshh/AI_planet_Devops/tree/main/API_manifest_repo) (For storing manifest files.)

You can check those directory just by clicking on above names.


  












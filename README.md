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


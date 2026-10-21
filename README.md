DevOps-Project
The project contains terraform file which creates EC2 instance with ssh-key so we can log in.

Once the EC2 instance is started, Jenkins is installed automatically.

The terraform file creates also an ECR (Elastic Container Registry) where I will keep the docker images.

The Dockerfile builds the application from Github.

Multibranch pipeline is used in Jenkins to build Jenkinsfile if it is available in the branch.

The Jenkinsfile includes the following steps:

builds the Dockerfile
push it into the ECR
deploys the helm chart in Kubernetes by passing the tag dynamically

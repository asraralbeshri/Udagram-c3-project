
# Udagram app
The Udagram is a simple cloud application developed alongside the Udacity Cloud Engineering Nanodegree. It allows users to register and log into a web client, post photos to the feed and display the photos.
### Installing project dependencies
This project uses NPM to manage software dependencies. NPM Relies on the package.json files located in the project repositories. After cloning, open your terminal and run:

`npm install`
*tip: npm i is shorthand for npm install*

### Installing useful tools
1. [Postbird](https://electronjs.org/apps/postbird)
Postbird is a useful client GUI (graphical user interface) to interact with our provisioned Postgres database. We can establish a remote connection and complete actions like viewing data and changing schema (tables, columns, ect).
2. [Postman](https://www.getpostman.com/)
Postman is a useful tool to issue and save requests. Postman can create GET, PUT, POST, etc. requests complete with bodies. It can also be used to test endpoints automatically.
3. [Docker](https://www.docker.com/)
Docker is a platform to develop, deploy, and run applications inside containers
4. [Kubernetes](https://kubernetes.io/)
Kubernetes (K8s) is an open-source system for automating deployment, scaling, and management of containerized applications.
### Building and deploy Images
Open a new terminal within the project directory and run:

1. Build the images: `docker-compose -f docker-compose-build.yaml build --parallel`
2. Push the images: `docker-compose -f docker-compose-build.yaml push`
3. Run the container: `docker-compose up`


 ## Important Files and Project Structure
The project contains three repositories. The source code for this project resides in each ./src directory for each repository.
### - The important files in feed and user repositories
#### src/server.ts
The main code for the services is in the ./src/server.ts file for each repository.
#### routes/feed.router.ts 
Javascript file contains a list of feed services. It is useful for uploads and saves images in the database. It resides in m-udacity-resapi-feed/src/controllers/v0/feed/routes/feed.router.ts file.
#### routes/user.routes.ts 
Javascript file contains a list of user services. It is useful for registers and saves users in the database. It resides in m-udacity-resapi-user/src/controllers/v0/user/routes/user.router.ts file.
### - The important files in deployment repository:
#### docker-compose-build.yaml
The file is useful for building and pushing docker images to the docker hub.
#### deployment files 
These are files for creating deployment pods in the cluster. An example is backend-feed-deployment.yaml.
#### deploymet services
These are files for giving pods their IP addresses and a single DNS name for these Pods, and load-balance across them. An example is backend-feed-service.yaml.
#### env-configmap.yaml
The file contains environment variables.
#### env-secret.yaml and aws-secret.yaml
These are files for containing secret information.

### deployment basic commands
Open a new terminal within the project directory to do the following commands for kubernetes deployment:
1. Create the Deployment by running the following command
`kubectl apply -f {deploment file}`
exmple:
`kubectl apply -f backend-feed-deployment.yaml`
2. Run `kubectl get deployments` to check if the Deployment was created.
3. To see the Deployment rollout status, run `kubectl rollout status deployment backend-feed`
 see [Kubernetes deployment documentation ](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) for more useful commands.



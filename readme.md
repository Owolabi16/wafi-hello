
This deployment is done usind the following stacks

Jenkins ⚡️⚡️⚡️⚡️⚡️
Kubernetes✨
Docker✨
Temporal-server✨
Golang✨
Lets Get into it shall we... We start first with the setup of the temporal server and we use Docker-compose for this setup by editing some files and ensure the server and it's relevant dependencies are set-up

RUN THE FOLLOWING COMMAND

cd Kubernetes docker-compose up -d

After the server is up and running we setup the cluster that will be deployed using terraform.

We write a terraform configuration file to achieve this deployment.Which is not a subject of this deployment

We Then ensure the application is set-up and we run it using the following command
go run ./worker/main.go


Since we see how this server operates lets examine how to work with CI/CD

Deploying a fault tolerant application using CI/CD running with a temporal-server
To deploy Temporal-server on a dashboard in a kubernetes environment run the following commands

cd kubernetes && cd k8s && kubectl apply -f .

And we have the Dashboard present HERE

<img width="960" alt="temporal" src="https://user-images.githubusercontent.com/111136362/216768464-62584a06-c2f5-407f-aef8-6a1565605a24.PNG">

Temporal UI on Kuberenetes

But lets look at it using the DevOps way

AS DevOps Engineers we use Jenkins to Deploy the workloads
We create a pipeline and then we deploy the workloads by using webhooks that has been proconfigured in the environments
Final Remarks
We see the importance of temporal server in ensuring resiliency and high availability of the instances
Ruuning temporal is very vital for running microservices applications that needs high resiliency

I once deployed a Java Microservice application with temporal and this application was great because temporal leveraged it's ability to send retries even when one services is down to ensure there is high availabilty at all times, without throwing up an error.

This service can be improved by building it's dependence and enusring the instances are made multiple for loadBalancing and redundance

That's the little i can discuss in this documentation. Thanks for making it to the end✊✊✊👊🏼🫰🫰.

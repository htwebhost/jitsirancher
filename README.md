# jitsirancher
Project to Install and run simple Jitsi-meet instance in Rancher

To complete this project you will need a Rancher Kubernetes cluster up and running if you do not have one up it is not to difficult to spin one up. I recommend checking out Adrian Goins channel on how to spin up a standalone rancher single node here 
https://www.youtube.com/watch?v=BW74EY56tUs

I am writing this Project to help those who need to get a simple jitsi-meet instance running in rancher. I looked around and was not able to find exactly what I was looking for, however there are several projects for jitsi running in kubernetes and I took a lot of my resources from the projects of https://github.com/sunsingerus/kubernetes-jitsi-install and the kubernetes example on the main docker jitsi-meet install page of github https://github.com/jitsi/docker-jitsi-meet/tree/master/examples/kubernetes

I ended up using the kubernetes yaml files from the jitsi-meet example main repo as a base to do the install. This install will install an instance on jitsi-meet with all the componets running in a single pod. I have not figured out how to scale the jvb componet yet as I am still learning rancher, kubernetes, and docker, however this should help you get a basic install going. Anyone who has ideas of how to scale this in rancher please comment. Later I hope to have a youtube tutorial up on how to do this and will have a link.


# Steps to Install jitsi-meet single pod in Rancher Cluster

1. First thing to do is log into your Rancher instance and create a Projects/Namespaces named EX: jitsi-project or whatever you want to call it inside the cluster you want to deploy to. For the reset of this tutorial I will use jitsi-project.

2. The next step is to then go into the jitsi-project namespace you created and then click on the Resources drop down menu then click on Secrets. Inside of secrets we need to create a new secret. I will give the secret a name of jitsi-config. Under scope make sure Available to all namespaces in this project is selected. Under Secrets Values in Key add these three keys one per a line JICOFO_COMPONENT_SECRET JICOFO_AUTH_PASSWORD and JVB_AUTH_PASSWORD for the values of each key input some random data EX: 8uyrig38756 then click save.

3. Next click on Resources Secrets then click on Certificates here you need to add a certificate either a legit certificate or self signed for my example I created a self signed one. The reason I had to do this was because the Rancher automatic selfsigned cert for the loadbalancer did not work for me and I had to use a self signed one.

4. Now we need to go into jitsi-project namespace by clicking on it. You should see Workloads, Load Balancing, Service Discovery, Volumes at the top click on Service Discovery. At the top right click on Import YAML where the 1 is at the top paste in the yaml code for jvb-service.yaml Under Import Mode select Namespace: in the box to the right click Add to a new namespace then in the box type jitsi then click Import at the bottom.

5. 

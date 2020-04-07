# jitsirancher
Project to Install and run simple Jitsi-meet instance in Rancher

To complete this project you will need a Rancher Kubernetes cluster up and running if you do not have one up it is not to difficult to spin one up. I recommend checking out Adrian Goins channel on how to spin up a standalone rancher single node here 
https://www.youtube.com/watch?v=BW74EY56tUs

I am writing this Project to help those who need to get a simple jitsi-meet instance running in rancher. I looked around and was not able to find exactly what I was looking for, however there are several projects for jitsi running in kubernetes and I took a lot of my resources from the projects of https://github.com/sunsingerus/kubernetes-jitsi-install and the Kbernetes example on the main docker jitsi-meet install page of github https://github.com/jitsi/docker-jitsi-meet/tree/master/examples/kubernetes

I ended up using the kubernetes yaml files from the jitsi-meet example main repo as a base to do the install. This install will install an instance on jitsi-meet with all the componets running in a single pod. I have not figured out how to scale the jvb componet yet as I am still learning rancher, kubernetes, and docker, however this should help you get a basic install going. Anyone who has ideas of how to scale this in rancher please comment. Later I hope to have a youtube tutorial up on how to do this and will have a link.


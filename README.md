![1_3yr6NnIOLjRJa_iOa1R4zQ](https://user-images.githubusercontent.com/19241898/235276725-e45106aa-8252-49d6-a506-6b9f358759da.png)
# MongoExpress Demo on Kubernetes
 Deploying MongoDB Application and accessing it from Mongo-Express UI on Kubernetes.

# Mongo Express
Web-based MongoDB admin interface written with Node.js, Express and Bootstrap3

# What is kubernetes ?
Kubernetes is open-source-container-orchestration system for automatating computer application deployment, scaling and management.

# What are the important key componenets in Kubernetes?
* Cluster:

A Kubernetes cluster is a set of nodes that run containerized applications. Containerized applications packages an app with its dependences and some necessary services. Each cluster also has a master (control plane) that manages the nodes and pods (more on pods below) of the cluster Kubernetes clustes allow containers to run across multiple machines and environments: virtual, phyical, cloud-based, and on-premises.


* Node:

> A Node is single machine in a cluster. A Node is a worker machine in Kubernetes and may be either a virtual or a physical machine, depending on the cluster. Each Node is managed by the Master.

* Pod:

Pods are the smallest, most basic deployable objects in Kubernetes. A Pod represents a single instance of a running process in your cluster. Pods contain one or more containers, such as Docker containers. When a Pod runs multiple containers, the containers are managed as a single entity and share the Pod's resources.

* MasterNode:

Master Node controls the state of the cluster. The master node is the origin for all task assignments. It coordinate processes such as scheduling, scaling, cluster state, updates

# Features #
* Connect to multiple databases
* View/add/delete databases
* View/add/rename/delete collections
* View/add/update/delete documents
* Preview audio/video/image assets inline in collection view
* Nested and/or large objects are collapsible for easy overview
* Async on-demand loading of big document properties (>100KB default) to keep collection view fast
* GridFS support - add/get/delete incredibly large files
* Use BSON data types in documents
* Mobile / Responsive - Bootstrap 3 works passably on small screens when you're in a bind
* Connect and authenticate to individual databases
* Authenticate as admin to view all databases
* Database blacklist/whitelist
* Custom CA and CA validation disabling
* Supports replica sets


# General Concepts
* A Pod is the smallest execution unit in Kubernetes, and an abstraction over containers. A container is a lightweight software that contains all the necessary tools, libraries and code to run an application.

  * kubectl exec -it <pod_name> -- /bin/bash to get a bash shell in the container.
  * kubectl logs <pod_name> to show information logged by a pod.
* A Deployment is a resource to describe how a ReplicaSet and Pod should behave.

  * kubectl create deploy <deployment_name> --image=<image_name> to create a basic deployment with minimal configurations.
  * kubectl edit deploy <deployment_name> to edit the configuration file of a deployment.
  * kubectl delete deploy <deployment_name> to delete a deployment.
  
* A ReplicaSet aims to maintain a stable set of Pods running at any given time. The number of Pods maintained is determined in the configuration file of a deployment.

* A Service exposes an application running on a set of Pods as a network service.

* A ConfigMap is used to store non-sensitive data in key-value pairs, and can be consumed as environment variables, command-line arguments, or as configuration files.

* A Secret is similar to a ConfigMap, but more towards storing sensitive data, such as passwords, OAuth tokens, and ssh keys.

  * echo -n '<password>' | base64 to generate a base64 encoded string to be used as password in Secret, though a better hashing algorithm should be used.

* A Namespace is akin to a virtual cluster to organize resources between multiple teams, versions or environments.
   * kubectl create namespace <name> to create a namespace.

* An Ingress manages external access to services in a cluster. It provides load balancing, SSL termination and name-based virtual hosting. An Ingress consists of an        Ingress Controller and Ingress Resource. An Ingress Controller reads information from an Ingress Resource then evaluates all the rules and manages redirections.


# Homework 12 - Task2. K8S
## Task:

1. Get information about your worker node and save it in some file

2. Create a new namespace (all resources below will create in this namespace)

3. Prepare deployment.yaml file which will create a Deployment with 3 pods of Nginx or Apache and service for access to these pods via ClusterIP and NodePort. 
> * Show the status of deployment, pods and services. Describe all resources which you will create and logs from pods

4. Prepare two job yaml files:
> * One gets content via curl from an internal port (ClusterIP)
> * Second, get content via curl from an external port (NodePort)

5. Prepare Cronjob.yaml file which will test the connection to Nginx or Apache service every 3 minutes.

## Steps:
 
* Get information about nodes and save in file:
```
echo "kubectl get nodes -o wide" > info_nodes.txt  && kubectl get nodes -o wide >> info_nodes.txt && echo -e "\n" >> info_nodes.txt
```
* Add detail information about kubemaster node in file info_nodes.txt
```
echo "kubectl describe nodes kubemaster" >> info_nodes.txt  && kubectl describe nodes kubemaster >> info_nodes.txt && echo -e "\n" >> info_nodes.txt
```
* Add detail information about kubenode node in file info_nodes.txt
```
echo "kubectl describe nodes kubenode" >> info_nodes.txt  && kubectl describe nodes kubenode >> info_nodes.txt && echo -e "\n" >> info_nodes.txt
```
File [info_nodes.txt](https://github.com/rlnq/homework12/blob/main/info_nodes.txt) with information about worker node
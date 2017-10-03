## Running Sentinel-Nodes on Kubernets@GCP :=

### First Install gcloud sdk on your machine:

	`$ curl https://sdk.cloud.google.com | bash`

### Restart Your Terminal and Enter:

	`$ gcloud init`
	`$ gcloud components install kubectl`

### Now Running Sentinel-Nodes on Kubernetes(Config Files in Sentinel-Kube Directory):

	`$ gcloud container clusters create 'Cluster-Name' --num-nodes=3`
	`$ kubectl create \
	   > -f geth-coonfigMap.yml \
	   > -f geth-Service.yml \
	   > -f geth-daemonSet.yml`

Note: Number of Nodes can be set accroding to your wish.

### Now If You Want to Check What's Happening inside the containers, You Can Do:

	`$ kubectl get pods`
	`$ kubectl exec 'pod-name' -i -t sh `
	`$ cd var/geth && geth attach ipc:geth.ipc`
	`> admin.peers`



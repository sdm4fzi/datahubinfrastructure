# Setup a initial cluster running [AASX server](https://github.com/admin-shell-io/aasx-server)

- Create a new Kubernetes cluster in the sdm4fzi project on [Okeanos](https://dashboard.okeanos.dev).
- Download the `kubeconfig.yaml` from the Okeanos dashboard.
- Install and setup `kubectl`.
- If you want to inspect the state of the cluster, we recommend using [k9s](https://k9scli.io/).
  - E.g. you can 
	```shell
	export KUBECONFIG=PATH-TO-DOWNLOADED-KUBECONFIG
	k9s
	```
- To setup the initial AASX server:
  - Apply the Kubernetes Manifests to your newly created cluster:
	```shell
	export KUBECONFIG=PATH-TO-DOWNLOADED-KUBECONFIG
	kubectl apply -f deployment.yaml
	kubectl apply -f service.yaml
	kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.8.0/cert-manager.yaml
	kubectl apply -f letsencrypt.yaml
	```
  - Now enter the ingress domain of your cluster (you can find it in the Okeanos dashboard) at the corresponding locations in `ingress.yaml` and:
	```shell
	kubectl apply -f ingress.yaml
	```
  - Now you should be able to reach the AASX server at your ingress domain with your browser. Note that you most probably will need to add the letsencrypt staging certificate to your browser. 


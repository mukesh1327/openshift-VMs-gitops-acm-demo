# openshift-virtualmachines-gitops-acm-demo
Demo to create and manage virtual machines in multi-clusters with openshift gitops.  

## Prereqisites

- Setup openshift Hub cluster and managed clusters 
- Install and Setup ACM in Hub cluster and add the managed clusters
- Install and configure Openshift-GitOps (ArgoCD) in Hub cluster
- Setup Managed Cluster sets and bind with the Openshift-GitOps namespace
- Label the managed cluster which need to be refered by application sets

## How to setup

Setup the virtualization operator on Managed cluster where VMs need to be deployed.  
```bash
oc create -f applicationset-openshift-virtualization-operator-install.yaml
```

Deploy the Virtual Machines in managed clusters according to the label added in managed clusters (Done in Hub cluster ACM cluster list).  
```bash
oc create -f applicationset-deploy-vm.yaml
```

## References
- https://github.com/0xFelix/gitops-demo

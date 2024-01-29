# Task 1: Helm Setup
## Download and Run Helm Setup Script:
```
wget https://s3.ap-south-1.amazonaws.com/files.cloudthat.training/devops/kubernetes-essentials/helm.sh
```
```
bash helm.sh
```

## Check Helm Version:
```
helm version
```
# Task 2: Setup WordPress
## Add Bitnami Repository:
```
helm repo add bitnami https://charts.bitnami.com/bitnami
```
```
helm repo list
```
## Search and Install WordPress Chart:
```
helm search repo wordpress
```
```
helm install wordpress-chart bitnami/wordpress
```
## Fetch and Extract WordPress Compressed File:
```
helm fetch bitnami/wordpress
```
```
ls
```
```
tar -xvzf wordpress-12.2.1.tgz
```
## Deploy WordPress:
```
helm install wordpress --generate-name
```
# Task 3: Verify WordPress Setup
## Verify Running Pods:
```
kubectl get pods
```
## Check MariaDB Pods (StatefulSet) and WordPress Frontend (Deployment):
```
kubectl get sts
```
```
kubectl describe sts
```
```
kubectl get deploy
```

## View Services and Note External IP:
```
kubectl get svc
```
```
kubectl get svc --namespace default -w wordpress-<timestamp>
```
## Open Browser and Access WordPress Site:
## Open the browser and paste the service endpoint noted in the previous step. Observe that the WordPress site is up and running.

# Task 4: Cleanup
## List Current Helm Releases:

```
helm ls
```
## Delete Helm Release:
```
helm delete <helm_Release_Name>
```
## Verify Deletion:
```
helm ls
```

# Delete KOPs cluster
```
kops --help
```
## Use the following command to verify the clusters you have
```
kops get clusters
```
## use the following command to delete the cluster
### kops delete cluster --name <cluster-name> --state s3://<cluster-name> --yes
### Replace <cluster-name> and <s3-bucket> with the actual values
```
kops delete cluster --name ctjgp-13-2024-01-19-16-01.k8s.local --state s3://ctjgp-13-2024-01-19-16-01.k8s.local --yes
```
## Now From AWS console terminate your JumpServer

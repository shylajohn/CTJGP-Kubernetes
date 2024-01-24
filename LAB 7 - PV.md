# Task 1 : Get Node Label and Create Custom Index.html on Node

## View worker nodes and their labels
```
kubectl get nodes --show-labels | grep role=node
```
## Make a note of the kubernetes.io/hostname label of one of the nodes

## SSH to one of the nodes
```
ssh -t ubuntu@<node_public_IP>
```
## Switch to root
```
sudo su
```
## Run the following commands on the node
```
mkdir /pvdir
```
```
echo Hello World! > /pvdir/index.html
```
```
exit
```
# Task 2 : Create a Local Persistent Volume

## Create a file named pv-volume.yaml using content given below
```
vi pv-volume.yaml
```
```
kind: PersistentVolume
apiVersion: v1
metadata:
  name: pv-volume
spec:
  storageClassName: manual
  capacity:
    storage: 1Gi
  accessModes:
    - ReadWriteMany
  hostPath:
    path: "/pvdir"
```
## Save and exit the editor
## Apply the pv-volume.yaml created in the previous step
```
kubectl apply -f pv-volume.yaml
```
## Check the created PersistentVolume
```
kubectl get pv
```
```
kubectl describe pv pv-volume
```


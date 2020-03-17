# gcloud-kubectl

Original image: `https://github.com/GoogleCloudPlatform/cloud-builders/tree/master/kubectl`

Docker image to perform commands in gcloud kubernetes-cluster

---

#### Define variables

```
# Set region for regional GKE clusters or Zone for Zonal clusters
CLOUDSDK_COMPUTE_REGION=<your cluster's region>
# or
CLOUDSDK_COMPUTE_ZONE=<your cluster's zone>
```

| VAR | Description |
| ------ | ----------- |
| CLOUDSDK_COMPUTE_REGION   | Which region the VM is hosted |
| CLOUDSDK_COMPUTE_ZONE | Which zone the VM is hosted |
| CLOUDSDK_CONTAINER_CLUSTER    | name of the cluster |
| CLOUDSDK_API_KEY    | Base64 encoded json-key for the service account |
| CLOUDSDK_CORE_PROJECT | The project ID |


#### Example
```
docker run -e CLOUDSDK_COMPUTE_ZONE=europe-north1-a \
    -e CLOUDSDK_CONTAINER_CLUSTER=test-cluster \
    -e CLOUDSDK_CORE_PROJECT=test-21230 \
    -e CLOUDSDK_API_KEY=$key \
    simonjansson/gcloud-kubectl:latest \
    kubectl get deployments
```

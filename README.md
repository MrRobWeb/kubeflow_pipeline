# Basic kubeflow-pipeline

First of all, if you use a local setup it is recommended to create a virtual environment (venv).

Make sure that you've properly installed docker, k8s and kubeflow.

My setup is:
- docker-desktop for linux Ubuntu: https://docs.docker.com/desktop/setup/install/linux/ubuntu/ 
- minikube: https://minikube.sigs.k8s.io/docs/start/?arch=%2Flinux%2Fx86-64%2Fstable%2Fbinary+download
- kubeflow for docker-destop: https://www.kubeflow.org/docs/components/pipelines/legacy-v1/installation/localcluster-deployment/#docker-desktop


## Start kubeflow ui

```shell
kubectl port-forward -n kubeflow svc/service/ml-pipeline-ui 8080:80
```
Check if kubeflow is running:

```shell
kubectl get all -n kubeflow
```

## Create kubeflow pipeline

install kfp 

```shell
pip install kfp
```

run kubeflow_pipeline.py 

```shell
python kubeflow_pipeline.py 
```

create kubeflow pipeline

```shell
kfp pipeline create -p IrisProject kubeflow_pipeline.yaml
```

Now you can check in kubeflow if the project is created. Therefore, go to your internet browser:

http://localhost:8080/#/pipelines




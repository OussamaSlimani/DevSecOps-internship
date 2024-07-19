# Run a local Docker image in Minikube

---

## 1. Install Minikube

Go to this link and install Minikube in ububtu

- [minikube start](https://minikube.sigs.k8s.io/docs/start/?arch=%2Flinux%2Fx86-64%2Fstable%2Fbinary+download)

## 2. Install Kubectl

open the App center of ubuntu, search for "Kubectl" and install it.

## 3. Set up Minikube (image from dockerhub)

### 3.1. Start Minikube

```sh
minikube start
```

### 3.2. Set Docker Environment

Configure your shell to use the Docker daemon inside Minikube:

```sh
eval $(minikube docker-env)
```

### 3.3. Pull the image from the repository

```sh
docker pull oussamaslimani2001/flare-bank:testing
```

### 3.4. Verify the Image

Ensure the image is available in Minikube's Docker environment.

```sh
docker images
```

### 3.5. Create a Kubernetes Deployment

Create a YAML file (`deployment.yaml`) in the racine for the deployment:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: flare-bank-deployment
spec:
  replicas: 1
  selector:
    matchLabels:
      app: flare-bank
  template:
    metadata:
      labels:
        app: flare-bank
    spec:
      containers:
        - name: flare-bank
          image: oussamaslimani2001/flare-bank:testing
          ports:
            - containerPort: 80
```

- Apply the Deployment:

```sh
kubectl apply -f deployment.yaml
```

### 3.6. Expose the Deployment

Create a service to expose the deployment. You can do this by creating a YAML file (`service.yaml`) in the racine for the service:

```yaml
apiVersion: v1
kind: Service
metadata:
  name: flare-bank-service
spec:
  type: NodePort
  selector:
    app: flare-bank
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
```

- Apply the service:

```sh
kubectl apply -f service.yaml
```

### 3.7. Access the Application

Get the URL for the service:

```sh
minikube service flare-bank-service --url
```

- This URL will allow you to access your application running inside Minikube.

### 3.8. Stop and delete the container running in Kubernetes

- Delete the associated Kubernetes resources (the deployment and service)

1. Stop and Delete the Deployment:

   ```sh
   kubectl delete deployment flare-bank-deployment
   ```

2. Delete the Service:
   ```sh
   kubectl delete service flare-bank-service
   ```

Stop and delete the Minikube cluster

1. Stop Minikube:

   ```sh
   minikube stop
   ```

2. Delete Minikube Cluster:
   ```sh
   minikube delete
   ```

---

## 4. Set up Minikube (image built from Dockerfile)

### 4.1. Start Minikube

```sh
minikube start
```

### 4.2. Set Docker Environment

Configure your shell to use the Docker daemon inside Minikube:

```sh
eval $(minikube docker-env)
```

### 4.3. Build the Docker Image in the Minikube repo

If you haven't already built the Docker image, you can build it inside Minikube's Docker daemon. If the image is already built on your local system, you can retag it.

```sh
docker build -t flare-bank:testing .
```

### 4.4. Verify the Image

Ensure the image is available in Minikube's Docker environment.

```sh
docker images
```

### 4.5. Create a Kubernetes Deployment

Create a YAML file (`deployment.yaml`) in the racine for the deployment:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: flare-bank-deployment
spec:
  replicas: 1
  selector:
    matchLabels:
      app: flare-bank
  template:
    metadata:
      labels:
        app: flare-bank
    spec:
      containers:
        - name: flare-bank
          image: flare-bank:testing
          ports:
            - containerPort: 80
```

- Apply the Deployment:

```sh
kubectl apply -f deployment.yaml
```

### 4.6. Expose the Deployment

Create a service to expose the deployment. You can do this by creating a YAML file (`service.yaml`) in the racine for the service:

```yaml
apiVersion: v1
kind: Service
metadata:
  name: flare-bank-service
spec:
  type: NodePort
  selector:
    app: flare-bank
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
```

- Apply the service:

```sh
kubectl apply -f service.yaml
```

### 4.7. Access the Application

Get the URL for the service:

```sh
minikube service flare-bank-service --url
```

- This URL will allow you to access your application running inside Minikube.

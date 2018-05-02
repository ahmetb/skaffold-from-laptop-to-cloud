# 3. Use Skaffold to build & run apps remotely on GKE

This will:
- submit your source code to Google Cloud Container Builder (GCB)
- GCB push your image onto Google Container Registry (GCR)
- Skaffold will deploy it on Google Kubernetes Engine (GKE).

If you managed to run the voting app locally (Minikube or DockerForDesktop),
you can easily run it one GKE by just changing the image name.

### Before you begin, do these

1. Create a GKE cluster and make sure your `kubectl` is configured to use it.
2. Enable Google Container Registry (GCR) API
3. Enable Google Container Builder (GCB) API
4. Install GCR credentials helper:

    gcloud components install -q docker-credential-gcr
    gcloud auth configure-docker -q

### Steps

1. Take a look at the modified [skaffold.yaml](./skaffold.yaml). Prepend
  `gcr.io/YOUR_PROJECT/` string to `imageName:` fields.

1. In the same file, change `YOUR_PROJECT` under the `profiles:` section.

1. Visit the following files and update the `image:` field with these:

    - [voting-app/result-deployment.yaml](../voting-app/k8s-specifications/result-deployment.yaml)
    - [voting-app/worker-deployment.yaml](../voting-app/k8s-specifications/worker-deployment.yaml)
    - [voting-app/vote-deployment.yaml](../voting-app/k8s-specifications/vote-deployment.yaml)

    Don't worry about tagging. Skaffold automatically handles that.

1. Run:

    ```
    skaffold dev -p gcb -f 30-remote-build-to-gke/skaffold.yaml
    ```

Now, Skaffold is uploading your source code to GCB, which pushes the resulting
images to your GCR registry and it uses the active cluster on `kubectl` to
deploy the result. 

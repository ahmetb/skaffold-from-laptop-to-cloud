# 2. Use Skaffold to build & run apps locally on Docker for Desktop

- (If you have Minikube running, stop it with `minikube stop`, otherwise it
  will be used.)
- Download and install "Docker for Mac"
- Go to Docker's Settings and enable "Kubernetes"
- Wait until Kubernetes is enabled, run `kubectl get nodes` to verify.
- Make sure your current context is docker-for-desktop:

  ```sh
  kubectl config current-context docker-for-desktop


At this point you can just reuse the [same Skaffold manifest
file][ff] you used for Minikube.

Run:

```
skaffold dev -f 10-local-build-run-with-minikube/skaffold.yaml
```

This will build all images and deploy everything.

Visit the `vote` app at http://localhost:31000 and the `result` app at
http://localhost:31001.

Make a change to the app and watch Skaffold rebuild the image and redeploy it.

[ff]: ../10-local-build-run-with-minikube/skaffold.yaml

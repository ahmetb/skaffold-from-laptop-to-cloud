# 1. Use Skaffold to build & run apps locally on Minikube

Start `minikube` (verify via `minikube status`).

Skaffold will automatically detect you have minikube turned on.

Run:

```
skaffold dev -f 10-local-build-run-with-minikube/skaffold.yaml
```

This will build all images and deploy everything.

Run `minikube service vote` & `minikube service result` to visit the apps.

Make a change to one of the apps and watch `skaffold dev` rebuild and redeploy
the manifests.

Hit Ctrl+C to once to exit (cleanup will take some time).

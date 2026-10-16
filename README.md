# CloudOps Argo CD lab

Personal local Kubernetes GitOps exercise. Argo CD watches `main`, path `kubernetes`, and targets only `cloudops-lab` on the local cluster. Sync is manual; automated sync, prune and self-heal are disabled.

The app has two unprivileged NGINX replicas, readiness/liveness probes and a ClusterIP Service. The namespace enforces restricted Pod Security. No cloud resources, credentials or public ingress are configured. The image version is pinned but has not been vulnerability-scanned in this exercise.

Edit manifests, review changes, commit and push; inspect the Argo CD diff before manually syncing. Readiness drills can leave the app OutOfSync until manually reconciled.

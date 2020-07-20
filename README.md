# An Opsani servo for ArgoCD Rollouts controller

This servo is intended to support adjust against a deployment that is managed via a Rollout. We will initially focus on blue-green rollouts, and in a load-gen test mode where the rollouts are automatically promoted to "production"

ArgoCD Rollouts are a function designed to support models beyond what the standard Deployment controller in Kubernetes is capable of doing. The most basic version of this is a canary where, much like a Deployment, a single resource is upgraded at a time.  But in a Rollout canary, it is possible to do 1, then a percentage, and then the rest, whereas the k8s controller doesn't allow this through a Deployment.  The Blue-Green model is similiar in that it deploys based on a complete alternate deployment and a flip/flop model of promotion, e.g. replace one with the other.

In all cases, Rollouts support a wide variety of functions that are far beyond what is needed for Opsnai application tuning, and the goal of this servo is to simplify integration into applications that are deployed on Kubernetes with Argo rollouts in order to maintain consistency in the CI/CD process.

Future support for rollouts in-production will likley also be supported with a single resource auto-promoted blue-green rollout.

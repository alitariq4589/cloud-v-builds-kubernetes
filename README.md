# cloud-v-builds-kubernetes
Software release builds running in kubernetes on Milk-V Pioneer Box for CI packages

Dependencies: Kubernetes with control plane and worker nodes on milkv pioneer box

## Getting started

Get the token from the repository action settings of every package set up with CI.

Execute following command one time after setting up machine for kubernetes.

```
kubectl create namespace github-runners
```

Use following command to add repository (execute for each repository)

```
kubectl -n github-runners create secret generic github-runner-tokens \
  --from-literal=kubernetes-riscv-token=$TOKEN
kubectl apply -k ci-overlays/kubernetes-riscv
```
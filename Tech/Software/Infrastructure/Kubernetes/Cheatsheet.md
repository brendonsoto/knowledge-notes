---
aliases: 
created: 2022-01-18, 5:56:48 pm (Tuesday, January 18th)
updated: 2022-04-14, 9:23:17 am (Thursday, April 14th)
---
https://kubernetes.io/docs/reference/kubectl/cheatsheet/

- view current cluster: `kubectl config view`
- quickly see which cluster is current: `kubectl config current-context`
- switch cluster: `kubectl config use-context <name>`


**Note**: [autocompletion](https://kubernetes.io/docs/tasks/tools/included/) can help.


### Find a pod instance for service

`kubectl get pods --context=<ctx> | grep <service>`

### Get Logs on pod instance

Output latest:

`kubectl logs --context=<ctx> <service-instance>`



### View configs

`kubectl --context=<ctx> get configmap <service> -o yaml`

### Get secrets

Note that they're base-64 encoded

`kubectl --context <ctx> get secret <service> -o yaml`

### Set secrets

Note you'll need to base-64 encode it first

`kubectl --context <ctx> edit secret <service>`

### Get Secret + Set it without writing to bash history

`DATABASE_URL=$(kubectl get secret <service> --context <ctx> -ojsonpath='{.data.DATABASE_URL}' | base64 --decode)`

**for non-secrets**, you can use `configmap` in place of secret

### How to do port forwarding

`helm status --kube-context=<ctx> --tiller-namespace default --tls <service>`

### Run a shell on a running container
`kubectl exec --stdin --tty <name-of-container> -- /bin/sh`

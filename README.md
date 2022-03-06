# ArgoCD ApllicationSets Bootstrap Sample

This scenario shows the basic deployment ArgoCD with ApplicationSet Git Generator:Directories

Check if kubernetes is up and running(It can take some time):

```kubectl cluster-info```

Clone the sample App Of Apps implementation to current directory:

```git clone https://github.com/a1tan/argoapplicationsets.git```


Install the ArgoCD application:

```kubectl apply -k argoapplicationsets/managementstack/argocd```

This will install ArgoCD controllers and ApplicationSet controllers to argocd namespace.

Wait until all resources up and running(It can take some time):

```kubectl get pods -n argocd -w```


Apply the applicationset definition:

```kubectl apply -k argoapplicationsets/managementstack/argocdapplications```



Check if applications installed and synchronized:

```kubectl get application -n argocd -owide -w```

If you want to change settings of ArgoCD and watch auto sync operations, just take this code and push to your own repository.
After you follow the same steps with your own repository you can change ArgoCD setup by pushing changes.
Or you can add your own applications under managementstack folder.

# Deploy

```
minikube start
kubectl apply -f deployment.yaml
```

#Pruebas

## Mediante curl 

```
kubectl get pods //obtener nombre de los pods

kubectl exec -it passwordapi-5dd5f46c96-4plr7 --  bash //ingresar a uno

curl localhost:3000/password  //realizar un curl
```

// Ejemplo de salida

```
(master) alan@alan-vb:~/repo/docker-kub/ejercicio09$ kubectl exec -it passwordapi-5dd5f46c96-4plr7 --  bash
root@passwordapi-5dd5f46c96-4plr7:/usr/src/app# curl localhost:3000/password
{"password":"!053OoYy>>Kk"}root@passwordapi-5dd5f46c96-4plr7:/usr/src/app#
```


## Mediante forward de puertos

```
kubectl get pods //obtener nombre de los pods

kubectl port-forward pod/passwordapi-5dd5f46c96-4plr7 3000:3000 //elegir uno
```

Ingresar a http://localhost:3000/password




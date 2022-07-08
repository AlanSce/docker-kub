# Screenshot de deploy funcionando

![](https://github.com/AlanSce/docker-kub/blob/master/ejercicio14/ejer14.png)

# Pasos manuales que se hicieron

```
minikube addons enable ingress
kubectl expose deployment pingapp --type=NodePort --port=4567
kubectl expose deployment passwordapi --type=NodePort --port=3000
```

Se obtuvo la IP de minikube con: 

```
minikube ip
```

Y se configuró esa ip en `/etc/hosts` para que apunte al dominio que indicó la consigna. 

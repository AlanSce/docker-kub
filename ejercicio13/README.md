# Verificación 

Utilicé `kubectl describe` para ver si se levantaba bien. Noté que si ponía tiempos muy cortos, como por ejemplo un segundo, el contenedor se restarteaba.

Salida de ejemplo de contenedor listo: 

```
(master) alan@alan-vb:~/repo/docker-kub/ejercicio13$ kubectl describe pod/passwordapi-58888fdbd6-8z99m
Name:         passwordapi-58888fdbd6-8z99m
Namespace:    ejer13
Priority:     0
Node:         minikube/192.168.49.2
Start Time:   Thu, 07 Jul 2022 23:21:27 -0300
Labels:       app=passwordapi
              pod-template-hash=58888fdbd6
Annotations:  <none>
Status:       Running
IP:           172.17.0.6
IPs:
  IP:           172.17.0.6
Controlled By:  ReplicaSet/passwordapi-58888fdbd6
Containers:
  passwordapi:
    Container ID:   docker://178168de14f217a3b2132ff4be59247dc116998ffe1bad08f5ccef8de5bb3c8e
    Image:          nicopaez/password-api:1.5.0-java
    Image ID:       docker-pullable://nicopaez/password-api@sha256:d832f0ec4b639c342900a6cafda5733daabf8121b5dc5f583fe179055093fa87
    Port:           8080/TCP
    Host Port:      0/TCP
    State:          Running
      Started:      Thu, 07 Jul 2022 23:21:30 -0300
    Ready:          True
    Restart Count:  0
    Liveness:       http-get http://:8080/actuator/health delay=10s timeout=1s period=3s #success=1 #failure=3
    Readiness:      http-get http://:8080/actuator/health delay=10s timeout=1s period=3s #success=1 #failure=3
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-5xg8s (ro)
Conditions:
  Type              Status
  Initialized       True 
  Ready             True 
  ContainersReady   True 
  PodScheduled      True 
Volumes:
  kube-api-access-5xg8s:
    Type:                    Projected (a volume that contains injected data from multiple sources)
    TokenExpirationSeconds:  3607
    ConfigMapName:           kube-root-ca.crt
    ConfigMapOptional:       <nil>
    DownwardAPI:             true
QoS Class:                   BestEffort
Node-Selectors:              <none>
Tolerations:                 node.kubernetes.io/not-ready:NoExecute op=Exists for 300s
                             node.kubernetes.io/unreachable:NoExecute op=Exists for 300s
Events:
  Type    Reason     Age   From               Message
  ----    ------     ----  ----               -------
  Normal  Scheduled  105s  default-scheduler  Successfully assigned ejer13/passwordapi-58888fdbd6-8z99m to minikube
  Normal  Pulling    105s  kubelet            Pulling image "nicopaez/password-api:1.5.0-java"
  Normal  Pulled     103s  kubelet            Successfully pulled image "nicopaez/password-api:1.5.0-java" in 2.190071107s
  Normal  Created    103s  kubelet            Created container passwordapi
  Normal  Started    102s  kubelet            Started container passwordapi
```

# Conexión 

Una vez deployado todo, hago: 

```
(master) alan@alan-vb:~/repo/docker-kub/ejercicio12$ kubectl get pod
NAME                          READY   STATUS    RESTARTS   AGE
jobvacancy-59dcb7b67b-wkmn8   1/1     Running   0          48s
postgres-7c4bc8587-8rptf      1/1     Running   0          18m
(master) alan@alan-vb:~/repo/docker-kub/ejercicio12$ kubectl port-forward jobvacancy-59dcb7b67b-wkmn8 3000
Forwarding from 127.0.0.1:3000 -> 3000
Forwarding from [::1]:3000 -> 3000
Handling connection for 3000
```
E ingresando a `localhost:3000` puedo manipular la aplicación. 


# Prueba de que los datos se guardan correctamente en la base

```
(master) alan@alan-vb:~/repo/docker-kub/ejercicio12$ kubectl exec -ti postgres-7c4bc8587-8rptf -- bash
root@postgres-7c4bc8587-8rptf:/# psql -U myuser base
psql (10.4 (Debian 10.4-2.pgdg90+1))
Type "help" for help.

base=# \dt;
           List of relations
 Schema |    Name     | Type  | Owner  
--------+-------------+-------+--------
 public | job_offers  | table | myuser
 public | pings       | table | myuser
 public | schema_info | table | myuser
 public | users       | table | myuser
(4 rows)

base=# select * from job_offers;
 id |       title       | location | description | user_id | created_on | updated_on 
| is_active 
----+-------------------+----------+-------------+---------+------------+------------
+-----------
  1 | Infra para fierro | remoto   | sarasa      |       1 | 2022-07-07 | 2022-07-07 
| t
(1 row)

base=# 

```

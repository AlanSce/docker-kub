# Prueba de que los datos se guardan correctamente en la base

```
(master) alan@alan-vb:~/repo/docker-kub/ejercicio12$ kubectl exec -ti pgstateful-0 -- bash
root@pgstateful-0:/# psql -U myuser base
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
  1 | Infra para fierro | remoto   | sarasa      |       1 | 2022-07-06 | 2022-07-06 
| t
(1 row)

base=# 
```
Si borro el pod de postgresql, los datos no persisten. 


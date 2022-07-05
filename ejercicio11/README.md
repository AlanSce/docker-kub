#Conversión del secret a base64

```
echo -n '{"mypass":"password!"}' | openssl base64

Salida:
eyJteXBhc3MiOiJwYXNzd29yZCEifQ==
```

#Salida

```
appuser@pingapp-d8c68c957-4kfwl:/apps/pingapp$ echo $CONFIG_LOCATION
/mydata/config.json
appuser@pingapp-d8c68c957-4kfwl:/apps/pingapp$ echo $SECRETS_LOCATION
/mysecrets/secret.json
appuser@pingapp-d8c68c957-4kfwl:/apps/pingapp$ curl localhost:4567/config
{'key1':'value1'}
```

#Conversión del secret a base64

```
echo -n '{"mypass":"password!"}' | openssl base64

Salida:
eyJteXBhc3MiOiJwYXNzd29yZCEifQ==
```

#Salida

```
appuser@pingapp-d8c68c957-hnfj8:/apps/pingapp$ curl 10.103.123.4:4567
{"version":"2.1.0","ping":"2022-07-05T02:31:51+00:00","config_location":"/mydata/config.json","secrets_location":"/mysecrets/secret.json","host":"pingapp-d8c68c957-ltd6h"}

appuser@pingapp-d8c68c957-hnfj8:/apps/pingapp$ curl 10.103.123.4:4567/config
{'key1':'value1'}

appuser@pingapp-d8c68c957-hnfj8:/apps/pingapp$ curl 10.103.123.4:4567/secrets
{"mypass":"password!"}
```


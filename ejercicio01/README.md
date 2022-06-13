= Pasos para acceder a la pagina = 

1- Ejecutar el comando

`
docker run -d --name nginx-ejer01 -v $PWD/pagina:/var/www -v $PWD/conf/nginx.conf:/etc/nginx/nginx.conf -p 80:80 nginx
`

2- Ingresar desde un navegador a la direccion `localhost:80`

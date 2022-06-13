# Pasos para subir la imagen a Docker Hub 

1- Descargar la imagen con

`
docker pull nicopaez/pingapp:3.0.0
`

2- Ingresar a su cuenta de DockerHub y hacer clic en `Create Repository`. Elegir un nombre para el repositorio, por ejemplo `pingapp`. Asegurarse que en la seccion `Visibilidad` esté marcada la opción `Público`. Finalmente, presionar `Crear`. 

3- Desde la terminal, ejecutar

`
docker image tag nicopaez/pingapp:3.0.0 alansce/pingapp:3.0.0
`
4- Realizar el login para poder pushear la imagen 

`
docker login -u alansce
`

5- 

`
docker image push alansce/pingapp:3.0.0
`

# Para pullear la imagen

`
docker pull alansce/pingapp:3.0.0
`



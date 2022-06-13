# nicopaez/passwordapi-java:java8-alpine

Tiene 4 layers 

# nicopaez/passwordapi-java:java8-fabric


Tiene 9 layers 

# Layers en comun

Tienen el primer layer en comun, donde ambos usan la misma imagen base

`
FROM 3b2f672a71b0c0b
`

Y tienen otro layer en común donde copian la aplicacion (aunque lo hacen a directorios distintos): 


Para alpine
`
COPY file:a6e9b80e7469da50e389566bffb8669b6e40df0caeaf327465fb3d0162788101 in /app.jar
`

Para fabric

`
COPY file:a6e9b80e7469da50e389566bffb8669b6e40df0caeaf327465fb3d0162788101 in /deployments/app.jar
`





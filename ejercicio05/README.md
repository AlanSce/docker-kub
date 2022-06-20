#HEALTHCHECK

Este comando puede ser colocado en el DockerFile para que ejecute un comando cada cierto tiempo, y luego con un inspect podemos ver un registro de fallos y si el contenedor está "saludable".

Por ejemplo, a un docker file se le agregaría 

`
HEALTHCHECK --interval=35s --timeout=4s CMD curl -f https://localhost/ || exit 1
`

#ONBUILD 

Este comando permite que se ejecute una instrucción más tarde, más precisamente cuando se llame a esta imagen como base de otra. 

Actua como un trigger, donde permite dejar un comando que se va a ejecutar cuando otra imagen use a esta. 

#VOLUME

Crea un volumen montado para el host. Es decir, si en el Dockerfile agrego un `VOLUME /mydocker` crea el volumen montado para mi sistema Linux y para otros contenedores. 


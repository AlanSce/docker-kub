Se están ejecutando dos contenedores 

- ejercicio07_web_1 -> Basado en la imagen nicopaez/jobvacancy-ruby:1.3.0


- ejercicio07_db_1  -> Basado en la imagen de postgres oficial. 


docker-compose-jobvacancy.yml:
```
version: '2'
services:
  web: //declara contenedor web
    image: nicopaez/jobvacancy-ruby:1.3.0 //indica la imagen a utilizar
    links: // hace que el contenedor web pueda "encontrar" al contenedor db
      - db
    ports: //forward de los puertos 
      - "3000:3000"
    environment: //le pasa al contenedor variables de entorno 
      PORT: "3000"
      RACK_ENV: "production"
      DATABASE_URL: "postgres://postgres:Passw0rd!@db:5432/postgres"
    depends_on: //hace que el contenedor web espere a que el contenedor db esté en estado started. 
      - db
  db: //declara contenedor de base de datos
    image: postgres //indica la imagen a utilizar
    environment:
      POSTGRES_PASSWORD: Passw0rd! //le pasa al contenedor una variable de entorno
```
Los contenedores se ven entre sí a través del comando links. Entiendo que web puede ver a db, pero db no puede ver a web. No pude encontrar si esto es así, o si al declarar link en uno, los dos se pueden encontrar. 

Entiendo que al declararse como en el ejemplo, el contenedor web puede encontrar a db para hacer una petición y que éste responda, pero db no podría hacerle una petición al contenedor web.

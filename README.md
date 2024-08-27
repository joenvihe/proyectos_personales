# PROYECTOS PERSONALES

El siguiente repositorio integra los proyectos personales que voy realizando como primeras pruebas de concepto en mi servidor de digital ocean, actualmente contiene mi Pagina Web Personal, mi proyecto chatdocument que te permite chatear con diferentes documentos y tambien un scrapeo de la bolsa de valores de lima.

Para levantar mis aplicaciones utilizo docker compose como un proxy inverso y tambien un servidor en nginx para levantar mi web personal como tambien el SSL

# Configuracion
Esta confirguracion permite levantar la pagina web personal enrique.vicenteh.com y el chatdocumento enrique.vicenteh.com/chatdocument_app usando docker compose:

- Crear la carpeta ./certs
- Crear el certificado SSL:
"sudo certbot certonly --standalone -d enrique.vicenteh.com --register-unsafely-without-email --agree-tos"
- Copiar los archivos resultados a la carpeta ./certs
$ cp /etc/letsencrypt/live/enrique.vicenteh.com/fullchain.pem ./certs/fullchain.pem
$ cp /etc/letsencrypt/live/enrique.vicenteh.com/privkey.pem ./certs/privkey.pem
- clonar los proyectos
$ git clone app_enriquevicenteh
$ git clone chatdocument_app
- ejecutar el compose:
$ docker-compose up --build --force-recreate -d
$ docker-compose down  # para bajar los servicios
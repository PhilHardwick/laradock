FROM mhart/alpine-node
MAINTAINER Johannes Schickling "schickling.j@gmail.com"

ENV VERSION "v2.1.4"
ENV FOLDER "swagger-ui-master"
ENV API_URL "http://petstore.swagger.io/v2/swagger.json"
ENV API_KEY "**None**"
ENV WORKING_DIR "/app"
ENV REL_SWAGGER_JSON "swagger-configuration/swagger.json"
ENV ABS_SWAGGER_JSON "/app/swagger-configuration/swagger.json"

WORKDIR /app

RUN apk update && apk add openssl
RUN wget -q https://github.com/swagger-api/swagger-ui/archive/master.zip
RUN unzip master.zip
RUN cp -r $FOLDER/dist/* . && rm -rf $FOLDER
RUN npm install -g http-server
RUN apk del openssl

ADD run.sh run.sh

# webserver port
EXPOSE 80

CMD ["sh", "run.sh"]
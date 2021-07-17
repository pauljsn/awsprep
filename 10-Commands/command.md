# Docker

### Passing ENV Variables - Command Line
* docker run -it —env LOG_DIR=‘/tmp/logs’ -p8080:8080 my-api

### Passing ENV variables - Docker File
* ENV APP_DIR /prod/usr

* COPY blah/blah ${APP_DIR}/
* RUN chmod +x ${APP_DIR}/bin/startup.sh
* CMD ${APP_DIR}/bin/startup.sh

RUN apk —no-cache add curl

### To run in background
* docker-compose up -d #to send to background


# Network
* nclookup
* nc -vz $HOST $PORT
* wget $URL
* nmap -p $PORT $IP


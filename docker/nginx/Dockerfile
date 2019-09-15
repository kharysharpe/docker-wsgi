FROM nginx:1.17.3
LABEL maintainer="Khary Sharpe <ksharpe@email.com>"

RUN DEBIAN_FRONTEND="noninteractive" apt-get clean && apt-get update

COPY ./resources/config/default.conf /etc/nginx/conf.d/default.conf

EXPOSE 8080
EXPOSE 8443

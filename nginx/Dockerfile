FROM nginx

ENV TimeZone=Asia/Shanghai

WORKDIR /etc/nginx/
RUN cp nginx.conf ./nginx.conf.bak
COPY ./conf/nginx.conf ./

CMD mkdir tcp_conf
CMD mkdir firewall_conf
COPY ./conf/tcp_conf/* ./tcp_conf/
COPY ./conf/firewall_conf/* ./firewall_conf/

CMD mkdir -p /var/www/static

WORKDIR /var/www/static
COPY ./templates/index.html ./index.html

CMD ["nginx", "-g", "daemon off;"]

EXPOSE 80
EXPOSE 7000
EXPOSE 8080
EXPOSE 8081
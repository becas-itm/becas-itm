FROM nginx:1.19-alpine

ENV WAITFORIT_VERSION="v2.4.1"
RUN wget -q -O /usr/local/bin/waitforit https://github.com/maxcnunes/waitforit/releases/download/$WAITFORIT_VERSION/waitforit-linux_amd64 \
    && chmod +x /usr/local/bin/waitforit

COPY nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80

COPY --from=becas/web /usr/src/app/web/ /etc/nginx/html

CMD [ "nginx", "-g", "daemon off;" ]

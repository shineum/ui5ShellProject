FROM nginx:1.23.1-alpine

ARG GIT_OWNER=shineum
ARG GIT_PROJECT=ui5Components
ARG GIT_URL=https://github.com/${GIT_OWNER}/${GIT_PROJECT}.git

RUN mkdir -p /opt/apps/html
WORKDIR /opt/apps
RUN apk add git
RUN git clone ${GIT_URL} html
RUN cp /usr/share/nginx/html/50x.html /opt/apps/html
RUN sed 's|/usr/share/nginx/html|/opt/apps/html|' -i /etc/nginx/conf.d/default.conf

EXPOSE 80
CMD ["/usr/sbin/nginx", "-g", "daemon off;"]
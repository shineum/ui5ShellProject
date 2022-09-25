FROM nginx:1.23.1-alpine

# https://openui5.org/releases/
# https://github.com/SAP/openui5/releases/download/1.106.0/openui5-runtime-1.106.0.zip

ARG OPENUI5_VER=1.106.0
ARG OPENUI5_FILE=openui5-runtime-${OPENUI5_VER}.zip

WORKDIR /usr/share/nginx/html
RUN wget https://github.com/SAP/openui5/releases/download/${OPENUI5_VER}/${OPENUI5_FILE}
RUN unzip -o $OPENUI5_FILE
RUN rm $OPENUI5_FILE

EXPOSE 80
CMD ["/usr/sbin/nginx", "-g", "daemon off;"]
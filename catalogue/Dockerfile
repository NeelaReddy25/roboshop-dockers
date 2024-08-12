FROM node:20.15.0-alpine3.20
EXPOSE 8080
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop \
    && mkdir /opt/server \
    && chown roboshop:roboshop -R /opt/server
WORKDIR /opt/server
ENV MONGO=true
COPY package.json /opt/server/
COPY *.js /opt/server/
RUN npm install
USER roboshop
CMD ["node","server.js"]

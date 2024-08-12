FROM node:20.15.0-alpine3.20
EXPOSE 8080
ENV MONGO=true
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop \
    && mkdir /opt/server \
    && chown roboshop:roboshop -R /opt/server
WORKDIR /opt/server
COPY package.json .
COPY server.js /opt/server/
RUN npm install
CMD ["node","server.js"]
FROM node:20
EXPOSE 8080
ENV MONGO=true
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
RUN mkdir /opt/server 
RUN chown roboshop:roboshop -R /opt/server
WORKDIR /opt/server
COPY package.json /opt/server/
COPY *.js /opt/server/
RUN npm install
USER roboshop
CMD ["node","server.js"]

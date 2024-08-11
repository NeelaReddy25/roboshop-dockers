FROM node:20
EXPOSE 8080
RUN useradd roboshop
RUN mkdir /opt/server 
RUN chown roboshop:roboshop -R /opt/server
WORKDIR /opt/server
ENV MONGO=true
COPY package.json /opt/server/
COPY *.js /opt/server/
RUN npm install
USER roboshop
CMD ["node","server.js"]

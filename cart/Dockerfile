FROM node:20
EXPOSE 8080
ENV REDIS_HOST=redis
ENV CATALOGUE_HOST=cataloguedd
RUN useradd roboshop \
    && mkdir /opt/server \
    && chown roboshop:roboshop -R /opt/server
WORKDIR /opt/server
COPY package.json .
COPY *.js /opt/server/
RUN npm install
USER roboshop
CMD ["node","server.js"]
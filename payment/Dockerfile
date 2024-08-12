FROM python:3.9.18-alpine3.19
EXPOSE 8080
ENV AMQP_USER=roboshop
ENV AMQP_PASS=roboshop123
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop \
    && mkdir /opt/server \
    && chown roboshop:roboshop -R /opt/server
WORKDIR /opt/server
COPY requirements.txt /opt/server/
RUN apk update && apk add --no-cache python3 py3-pip
RUN pip install -r requirements.txt
COPY *.py /opt/server/
COPY payment.ini /opt/server/
USER roboshop
CMD ["uswgi", "--ini", "payment.ini"]
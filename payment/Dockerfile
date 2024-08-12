FROM python:3.11-alpine3.20
EXPOSE 8080
USER root
ENV AMQP_USER=roboshop
ENV AMQP_PASS=roboshop123
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop \
    && mkdir /opt/server \
    && chown roboshop:roboshop -R /opt/server
WORKDIR /opt/server
COPY requirements.txt /opt/server/
RUN apk update && apk add --no-cache python3 py3-pip build-base python3-dev musl-dev linux-headers
# RUN apk update && apk add --no-cache python3 py3-pip
RUN pip install --upgrade pip
RUN pip install -r requirements.txt
COPY *.py /opt/server/
COPY payment.ini /opt/server/
CMD ["python3.11", "payment.py"]
# CMD ["uswgi", "--ini", "payment.ini"]
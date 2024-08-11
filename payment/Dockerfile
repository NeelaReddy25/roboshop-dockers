FROM python:3.11
EXPOSE 8080
ENV AMQP_USER=roboshop
ENV AMQP_PASS=roboshop123
RUN useradd roboshop \
    && mkdir /opt/server \
    && chown roboshop:roboshop -R /opt/server
WORKDIR /opt/server
COPY requirements.txt /opt/server/
RUN apt-get update && apt-get install -y python3.11
RUN pip install -r requirements.txt
COPY .py/* /opt/server/
COPY payment.ini /opt/server/
USER roboshop
CMD ["pyuswgi", "--ini", "payment.ini"]
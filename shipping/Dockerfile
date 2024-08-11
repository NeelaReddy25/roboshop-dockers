FROM maven AS build
EXPOSE 8080
ENV CART_ENDPOINT=cart
ENV DB_HOST=mysql
RUN useradd roboshop \
    && mkdir /opt/shipping \
    && chown roboshop:roboshop -R /opt/shipping
WORKDIR /opt/shipping
COPY pom.xml /opt/shipping/
# RUN mvn dependency: resolve
COPY src /opt/shipping/src
RUN package
RUN npm install
USER roboshop
CMD [ "java", "-Xmn256m", "-Xmx768m", "-jar", "shipping.jar" ]
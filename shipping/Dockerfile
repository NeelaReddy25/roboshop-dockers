FROM maven AS build
WORKDIR /app
ADD . .
RUN mvn dependency:resolve
RUN mvn package

FROM openjdk:8-jdk
EXPOSE 8080
WORKDIR /app
ENV CART_ENDPOINT=cart:8080
ENV DB_HOST=mysql
COPY --from=build /app/target/shipping-1.0.jar shipping.jar
CMD [ "java", "-Xmn256m", "-Xmx768m", "-jar", "shipping.jar" ]

# FROM maven:3.8.5-openjdk-11-slim AS build
# EXPOSE 8080
# ENV CART_ENDPOINT=cart:8080
# ENV DB_HOST=mysql
# RUN useradd roboshop \
#     && mkdir /opt/shipping \
#     && chown roboshop:roboshop -R /opt/shipping
# WORKDIR /opt/shipping
# # RUN mvn clean install
# COPY pom.xml /opt/shipping/
# RUN mvn dependency:resolve
# COPY src /opt/shipping/src
# RUN mvn package
# # COPY --from=build /opt/shipping/target/shipping-1.0.jar shipping.jar
# # CMD [ "java", "-Xmn256m", "-Xmx768m", "-jar", "shipping.jar" ]

# FROM openjdk:19-jdk-alpine3.16

# EXPOSE 8080

# WORKDIR /opt/shipping

# ENV CART_ENDPOINT=cart:8080
# ENV DB_HOST=mysql

# COPY --from=build /opt/shipping/target/shipping-1.0.jar shipping.jar

# CMD [ "java", "-Xmn256m", "-Xmx768m", "-jar", "shipping.jar" ]



# #Build

# FROM maven AS build

# WORKDIR /opt/shipping

# COPY pom.xml /opt/shipping/
# RUN mvn dependency:resolve
# COPY src /opt/shipping/src/
# RUN mvn package

# #
# # Run
# #
# FROM openjdk:19-jdk-alpine3.16

# EXPOSE 8080

# WORKDIR /opt/shipping

# ENV CART_ENDPOINT=cart:8080
# ENV DB_HOST=mysql

# COPY --from=build /opt/shipping/target/shipping-1.0.jar shipping.jar

# CMD [ "java", "-Xmn256m", "-Xmx768m", "-jar", "shipping.jar" ]


# FROM maven AS build

# WORKDIR /opt/shipping

# COPY pom.xml /opt/shipping/
# RUN mvn dependency:resolve
# COPY src /opt/shipping/src/
# RUN mvn package
# RUN mv /opt/shipping/target/shipping-1.0.jar shipping.jar
# CMD [ "java", "-Xmn256m", "-Xmx768m", "-jar", "shipping.jar" ]
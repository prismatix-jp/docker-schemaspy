FROM classmethod/openjdk-with-git:9-jdk

ENV DRIVER_URL http://central.maven.org/maven2/mysql/mysql-connector-java/5.1.46/mysql-connector-java-5.1.46.jar
ENV APP_URL https://github.com/schemaspy/schemaspy/releases/download/v6.0.0-rc2/schemaspy-6.0.0-rc2.jar

WORKDIR /app

COPY ./schemaspy.sh /app/schemaspy.sh
RUN apt upadte && apt install graphviz font-noto git && \
    apt install --no-install-recommends tzdata wget openssl  && \
    wget -O mysql-connector-java.jar ${DRIVER_URL} && \
    wget -O schemaspy.jar ${APP_URL} && \
    apt purge tzdata wget openssl && \
    rm -rf /var/lib/apt/lists/*

CMD /app/schemaspy.sh
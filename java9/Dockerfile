FROM classmethod/openjdk-with-git:9-jdk

WORKDIR /app

COPY ./schemaspy.sh /app/schemaspy.sh
ADD http://central.maven.org/maven2/mysql/mysql-connector-java/5.1.46/mysql-connector-java-5.1.46.jar /app/mysql-connector-java.jar
ADD https://github.com/schemaspy/schemaspy/releases/download/v6.0.0-rc2/schemaspy-6.0.0-rc2.jar /app/schemaspy.jar
RUN apt update && apt install graphviz fonts-noto git -y && \
    rm -rf /var/lib/apt/lists/*

CMD /app/schemaspy.sh
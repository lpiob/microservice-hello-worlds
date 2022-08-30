FROM eclipse-temurin:18-jdk as jdk

ADD . /app/

RUN cd /app/ && ls -laR && javac HelloWorld.java && jar cmvf META-INF/MANIFEST.MF HelloWorld.jar *.class

FROM eclipse-temurin:18-jre as jre

COPY --from=jdk /app/HelloWorld.jar /app/HelloWorld.jar
USER nobody
WORKDIR /app
EXPOSE 8080
CMD [ "java", "-Dhelloworld.port=8080", "-jar", "HelloWorld.jar" ]


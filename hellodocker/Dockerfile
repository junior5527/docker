FROM eclipse-temurin:11 as juniorbuilder
COPY src/Main.java /junior/src/Main.java
WORKDIR /junior
RUN javac -d ./build src/Main.java
WORKDIR /junior/build
RUN jar cfe hellodocker.jar Main Main.class




FROM eclipse-temurin:11
COPY --from=juniorbuilder  /junior/build/hellodocker.jar   /jc/mama.jar
CMD java -jar /jc/mama.jar
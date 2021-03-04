FROM maven:3.6.3-openjdk-8 AS packaging
RUN git clone https://github.com/wakaleo/game-of-life.git
RUN cd game-of-life && mvn package

FROM tomcat:jdk8-openjdk
COPY --from=packaging /game-of-life/gameoflife-web/target/gameoflife.war /usr/local/tomcat/webapps/gameoflife.war
EXPOSE 8080
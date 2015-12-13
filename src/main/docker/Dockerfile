# based on debian -> buildpack-deps:jessie-curl -> buildpack-deps:jessie-scm
FROM java:8

# Tomcat's working directories are created here by default.
VOLUME /tmp

# TODO: Refactor this naming convention to use environment variables
ADD bookmarks-0.0.1-SNAPSHOT.jar app.jar

# Static content requires a modification time.
RUN bash -c 'touch /app.jar'

# Reduce Tomcat startup time: http://wiki.apache.org/tomcat/HowTo/FasterStartUp#Entropy_Source
ENTRYPOINT ["java", "-Djava.security.egd=file:/dev/./urandom", "-jar", "/app.jar"]

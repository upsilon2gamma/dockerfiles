from openjdk:8

RUN cd /root/ && wget "https://services.gradle.org/distributions/gradle-4.4-bin.zip" && unzip gradle-4.4-bin.zip -d /opt/ && rm gradle-4.4-bin.zip

VOLUME ["/src", "/root/.gradle"]

WORKDIR "/src"

ENTRYPOINT ["/opt/gradle-4.4/bin/gradle"]

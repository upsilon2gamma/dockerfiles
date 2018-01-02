from openjdk:6

RUN cd /root/ && wget "https://services.gradle.org/distributions/gradle-2.14.1-bin.zip" && unzip gradle-2.14.1-bin.zip -d /opt/ && rm gradle-2.14.1-bin.zip

VOLUME ["/src", "/root/.gradle"]

WORKDIR "/src"

ENTRYPOINT ["/opt/gradle-2.14.1/bin/gradle"]

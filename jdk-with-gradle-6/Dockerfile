from openjdk:6

ENV GRADLE_VER=2.14.1
ENV GRADLE_BIN_ZIP="gradle-${GRADLE_VER}-bin.zip"
RUN cd /root/ && wget https://services.gradle.org/distributions/${GRADLE_BIN_ZIP} && unzip ${GRADLE_BIN_ZIP} -d /opt/ && mv /opt/gradle-${GRADLE_VER} /opt/gradle && rm ${GRADLE_BIN_ZIP}

VOLUME ["/src", "/root/.gradle"]

WORKDIR "/src"

ENTRYPOINT ["/opt/gradle/bin/gradle"]

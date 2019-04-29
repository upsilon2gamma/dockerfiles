from openjdk:8

# the latest version compatible with Android
ENV GRADLE_VER=4.10.2
ENV GRADLE_BIN_ZIP="gradle-${GRADLE_VER}-bin.zip"
RUN cd /root/ && wget https://services.gradle.org/distributions/${GRADLE_BIN_ZIP} && unzip ${GRADLE_BIN_ZIP} -d /opt/ && mv /opt/gradle-${GRADLE_VER} /opt/gradle && rm ${GRADLE_BIN_ZIP}

VOLUME ["/src", "/root/.android", "/root/.gradle"]

WORKDIR "/src"

ENTRYPOINT ["/opt/gradle/bin/gradle"]

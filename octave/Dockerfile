from upsilon2gamma/ubuntu-with-build-tools

# RUN apt-get update && apt-get install gcc g++ gfortran make libblas-dev liblapack-dev libpcre3-dev libarpack2-dev libcurl4-gnutls-dev epstool libfftw3-dev transfig libfltk1.3-dev libfontconfig1-dev libfreetype6-dev libgl2ps-dev libglpk-dev libreadline-dev gnuplot-x11 libgraphicsmagick++1-dev libhdf5-serial-dev openjdk-8-jdk libsndfile1-dev llvm-dev lpr texinfo libgl1-mesa-dev libosmesa6-dev pstoedit portaudio19-dev libqhull-dev libqrupdate-dev libqscintilla2-dev libqt4-dev libqtcore4 libqtwebkit4 libqt4-network libqtgui4 libqt4-opengl-dev libsuitesparse-dev texlive libxft-dev zlib1g-dev -y
RUN apt-get update && apt-get install gcc g++ gfortran make libblas-dev liblapack-dev libpcre3-dev libarpack2-dev libcurl4-gnutls-dev epstool libfftw3-dev transfig libfltk1.3-dev libgl2ps-dev libglpk-dev libreadline-dev libgraphicsmagick++1-dev libhdf5-serial-dev openjdk-8-jdk libqhull-dev libqrupdate-dev libqscintilla2-dev libsuitesparse-dev libxft-dev zlib1g-dev gnuplot-x11 libsndfile1-dev pstoedit portaudio19-dev libgl1-mesa-dev libosmesa6-dev -y

ENV JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64/
ENV OCTAVE_VER=4.2.1

WORKDIR /tmp
RUN wget "https://ftp.gnu.org/gnu/octave/octave-${OCTAVE_VER}.tar.gz"
RUN tar xzf octave-${OCTAVE_VER}.tar.gz && cd octave-${OCTAVE_VER} && ./configure --prefix=/opt/octave && make && make install && rm -rf /tmp/octave-${OCTAVE_VER}

WORKDIR /opt/octave
ENTRYPOINT ["bin/octave"]

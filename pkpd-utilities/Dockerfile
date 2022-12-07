ARG RELEASE_TAG
FROM bala001/cp-os-utilities:${RELEASE_TAG}

RUN echo "installing centos rpms..." \
    && echo "local repository file for centos8 rpms.." \
    && dnf install -y python36-devel \
    && dnf install -y  ImageMagick-c++ \
    ImageMagick \
    ImageMagick-devel \
    ImageMagick-c++-devel \
    poppler-devel \
    poppler-cpp-devel \
    poppler-data \
    poppler-cpp \
    poppler \
    #cabal-install \
    xorg-x11-utils \
    xorg-x11-fonts-cyrillic \
    xorg-x11-fonts-ISO8859-1-100dpi \
    #xorg-x11-proto-devel-2018 \
    xorg-x11-fonts-ISO8859-1-75dpi \
    xorg-x11-font-utils \
    xorg-x11-server-Xvfb \
    xorg-x11-xinit \
    xorg-x11-fonts-Type1 \
    xorg-x11-fonts-75dpi \
    xorg-x11-server-common \
    xorg-x11-xauth \
    xorg-x11-server-utils \
     xorg-x11-xbitmaps \
    xorg-x11-xkb-utils \
    xorg-x11-fonts-100dpi \
    openblas-openmp \
    blas \
    armadillo \
    #gdal-devel \
    #ghostscript \
    #ghostscript-fonts \
    #pandoc-citeproc \
  #  oracle-instantclient19.3-basic \
  #  oracle-instantclient19.3-devel \
  #  oracle-instantclient19.3-jdbc \
  #  oracle-instantclient19.3-odbc \
  #  oracle-instantclient19.3-precomp \
  #  oracle-instantclient19.3-sqlplus \
    && echo "clearing up RPMS local Repository" \
    && rm -rf /etc/yum.repos.d/Centos77-Local.repo \
    && yum clean all

RUN dnf install -y gnuplot-5.2.4-1.el8.x86_64 \
     pcre-8.42-6.el8.x86_64 \
     centos-linux-release-8.5-1.2111.el8.noarch \
     xorg-x11-server-Xvfb \
     libXt-devel-1.1.5-12.el8.x86_64 \
     libcurl-devel \
     gcc-8.5.0-4.el8_5.x86_64 \
     readline-devel-7.0-10.el8.x86_64 \
     pcre-devel-8.42-6.el8.x86_64 \
     bzip2-devel-1.0.6-26.el8.x86_64 \
     adobe-mappings-pdf-20180407-1.el8.noarch \
     libX11-1.6.8-5.el8.x86_64 \
      libX11-devel-1.6.8-5.el8.x86_64 \
     gcc-c++-8.5.0-4.el8_5.x86_64 \
     gcc-gfortran-8.5.0-4.el8_5.x86_64 \
     bzip2-1.0.6-26.el8.x86_64 \
     bzip2-libs-1.0.6-26.el8.x86_64 \
     qt-settings \
     libxml2-devel \
     openssl-devel \
     java-1.8.0-openjdk

RUN  echo "Installing Python Packages..." \
    && pip3 install mpmath \
    && pip3 install sympy  \
    && dnf install -y wget \
    && wget  https://github.com/wkhtmltopdf/packaging/releases/download/0.12.6-1/wkhtmltox-0.12.6-1.centos6.x86_64.rpm \
    && rpm -ivh wkhtmltox-0.12.6-1.centos6.x86_64.rpm \
    && rm -rf wkhtmltox-0.12.6-1.centos6.x86_64.rpm
     

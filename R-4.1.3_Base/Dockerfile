FROM cp-julia-1.7.3:2022q22-20220920232038603487765

COPY R-4.1.3.tar.gz /sources

RUN echo "Installing R-4.1.3 Base..." \
    && cd /sources \
#   && jfrog rt dl --flat ccssp-blob-generic-prod/R4-sources/R-4.1.1.tar.gz \
    && tar xvf R-4.1.3.tar.gz \
    && cd R-4.1.3 \
    && source /opt/rh/devtoolset-10/enable \
    && export CFLAGS='-O3 -march=core-avx-i -Wno-unused-variable -Wno-unused-function -Wno-builtin-macro-redefined' \
    && export CXXFLAGS=$CFLAGS \
    && ./configure --prefix=/pkpd/R-4.1.3 --enable-R-shlib --with-pcre1 --with-png --with-jpeg --without-x \
    && make \
    && make check \
    && make install \
    && make install-tests \
    && ln -s /pkpd/R-4.1.3/bin/R /pkpd/bin/R-4.1.3 \
    && ln -s /pkpd/R-4.1.3/bin/Rscript /pkpd/bin/Rscript-4.1.3 \
    && rm -rf /sources/R-4.1.3.tar.gz /sources/R-4.1.3

COPY Makevars /pkpd/R-4.1.3/lib64/R/etc/Makevars

COPY Renviron /pkpd/R-4.1.3/lib64/R/etc/Renviron

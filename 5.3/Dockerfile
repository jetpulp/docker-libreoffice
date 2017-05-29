FROM openjdk:7-jre


ENV LIBREOFFICEPACKAGE LibreOffice_5.3.3_Linux_x86-64_deb


RUN apt-get update && apt-get install -y --no-install-recommends \
      libxinerama1 \
      libgio-cil \
      libcairo2 \
      libdbus-glib-1-2 \
      libgl1-mesa-glx \
      libsm6 \
    && rm -rf /var/lib/apt/lists/* \
    && wget http://download.documentfoundation.org/libreoffice/stable/5.3.3/deb/x86_64/$LIBREOFFICEPACKAGE.tar.gz -O /tmp/libreoffice.tar.gz \
    && mkdir /tmp/LibreOffice \
    && tar -xzf /tmp/libreoffice.tar.gz -C /tmp/LibreOffice \
    && dpkg -i /tmp/LibreOffice/LibreOffice*/DEBS/*.deb \
    && rm -f /tmp/$LIBREOFFICEPACKAGE \
    && rm -rf /tmp/LibreOffice \
    && ln -s /usr/bin/libreoffice* /usr/bin/libreoffice


ADD run.sh /usr/local/bin/run.sh
CMD ["/bin/bash", "/usr/local/bin/run.sh"]

# Galaxy - deepTools
#
# VERSION       0.3

FROM bgruening/galaxy-stable:15.05

MAINTAINER Björn A. Grüning, bjoern.gruening@gmail.com

ENV GALAXY_CONFIG_BRAND deepTools

WORKDIR /galaxy-central

#RUN install-repository \
#    "--url https://testtoolshed.g2.bx.psu.edu/ -o iuc --name package_deeptools_1_5_10"

# Install deepTools
RUN install-repository \
    "--url https://testtoolshed.g2.bx.psu.edu/ -o bgruening --name deeptools --panel-section-name deepTools" \

# Install bowtie2, fastqc
    "--url https://toolshed.g2.bx.psu.edu/ -o devteam --name bowtie2 --panel-section-id solexa_tools" \
    "--url https://toolshed.g2.bx.psu.edu/ -o devteam --name fastqc --panel-section-id NGS_QC"

# Mark folders as imported from the host.
VOLUME ["/export/", "/data/", "/var/lib/docker"]

# Expose port 80 (webserver), 21 (FTP server), 8800 (Proxy)
EXPOSE :80
EXPOSE :21
EXPOSE :8800

# Autostart script that is invoked during container start
CMD ["/usr/bin/startup"]

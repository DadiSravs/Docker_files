ARG baseimageTag=latest
FROM debian:$baseimageTag
LABEL maintainer "Sravani"
LABEL email "sravanidadireddy96@gmail.com"
RUN echo "RUN one updated"
RUN apt update -y && apt install wget git curl -y
RUN echo "RUN two updated"
ENV PROJECT_HOME /opt/test
WORKDIR $PROJECT_HOME
RUN useradd Sravani -d /opt/test -s /bin/bash
COPY test.sh test.sh
ENV PATH "$PATH:/opt/test"
ARG branchName=develop
LABEL branchName $branchName
RUN chmod +x test.sh
USER Sravani
ENTRYPOINT ["test.sh"]

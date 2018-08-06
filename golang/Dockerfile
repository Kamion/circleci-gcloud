FROM circleci/golang

LABEL maintainer="Kamion Development team <hello@kamion.io>"

RUN apt-get install software-properties-common && \
    sudo apt-add-repository ppa:ansible/ansible && \
    apt-get update && \
    apt-get install ansible

RUN sudo chown -R circleci /usr/local/
RUN curl https://dl.google.com/dl/cloudsdk/release/google-cloud-sdk.tar.gz > /tmp/google-cloud-sdk.tar.gz
RUN mkdir -p /usr/local/gcloud
RUN tar -C /usr/local/gcloud -xvf /tmp/google-cloud-sdk.tar.gz
RUN /usr/local/gcloud/google-cloud-sdk/install.sh
ENV PATH $PATH:/usr/local/gcloud/google-cloud-sdk/bin

RUN gcloud components install kubectl

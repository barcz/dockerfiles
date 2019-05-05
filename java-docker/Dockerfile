FROM archlinux/base

RUN pacman -Syu
RUN pacman -S --noconfirm grep
RUN pacman -S --noconfirm wget
RUN pacman -S --noconfirm openssh
RUN pacman -S --noconfirm git
RUN pacman -S --noconfirm docker
RUN pacman -S --noconfirm jdk-openjdk
RUN pacman -S --noconfirm sbt

ENV HELM_VERSION="v2.13.1"

RUN wget -q https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl -O /usr/local/bin/kubectl \
    && chmod +x /usr/local/bin/kubectl \
    && wget -q https://storage.googleapis.com/kubernetes-helm/helm-${HELM_VERSION}-linux-amd64.tar.gz -O - | tar -xzO linux-amd64/helm > /usr/local/bin/helm \
    && chmod +x /usr/local/bin/helm

WORKDIR /config

CMD ['/bin/bash']
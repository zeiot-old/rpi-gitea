# Copyright 2017 Nicolas Lamirault <nicolas.lamirault@gmail.com>
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

# VERSION 1.3.2
# AUTHOR:         Nicolas Lamirault <nicolas.lamirault@gmail.com>
# DESCRIPTION:    zeiot/rpi-gitea

FROM resin/armv7hf-debian:stretch
MAINTAINER Nicolas Lamirault <nicolas.lamirault@gmail.com>

ENV GITEA_VERSION 1.3.2

ENV USER=git
ENV GROUP=git
ENV UID=1000
ENV GID=1000

RUN apt-get update && \
    apt-get install -y openssh-server git curl

RUN groupadd --gid ${GID} ${GROUP} \
    && useradd --uid ${UID} --gid ${GID} --shell /bin/bash ${USER}

ADD https://github.com/go-gitea/gitea/releases/download/v${GITEA_VERSION}/gitea-${GITEA_VERSION}-linux-arm-7 /gitea

RUN chmod +x /gitea && \
    mkdir /data && \
    mkdir /etc/gitea

ENV USER git
ENV GITEA_CUSTOM /data/gitea

VOLUME ["/etc/gitea", "/data/" ]

EXPOSE 22 3000

ENTRYPOINT [ "/gitea" ]

/ubuntu 18.04 tested/

apt-get update \
  && apt install -y git vim dnsutils curl sudo build-essential libssl-dev libffi-dev python-dev \
  && apt install -y python-pip && python -m pip install --upgrade pip \
  && curl -fsSL https://get.docker.com/ | sh || apt-get -y install docker.io\
  && ssh-keyscan -H github.com >> ~/.ssh/known_hosts \
  && curl -L "https://github.com/docker/compose/releases/download/1.27.4/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose && chmod +x /usr/local/bin/docker-compose \
  && git clone https://github.com/maxlim0/netflix-proxy.git && cd netflix-proxy
  && ./build.sh
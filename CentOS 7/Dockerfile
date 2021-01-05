FROM centos:7

RUN yum install -y \
git \
curl \
python2 \
ffmpeg \
libkrb5-dev \
vim \
nano \
gcc-c++ \
make \
cairo-devel \
libjpeg-turbo-devel \
pango-devel \
giflib-devel && \
curl -sL https://rpm.nodesource.com/setup_14.x | bash - && \
yum install -y nodejs && \
npm install -g pm2 && \
git clone https://github.com/galnir/Master-Bot.git ./Master-Bot
WORKDIR "/Master-Bot"
COPY ./config.json* .
COPY ./json.sqlite* .
RUN npm install
CMD ["pm2-runtime", "--raw", "index.js"]

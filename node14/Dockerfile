
FROM node:14

MAINTAINER foxiswho@gmail.com

ARG port
ENV PORT ${port:-4000}

ENV PROGRAM_HOME  /home
ENV PROGRAM_APP  /home/app

ENV TZ=Asia/Shanghai

EXPOSE ${PORT}

WORKDIR  ${PROGRAM_APP}

COPY app ${PROGRAM_APP}

RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone \
&& echo "alias ls='ls -lhG --color=auto'" >> /${PROGRAM_HOME}/node/.bashrc \
&& echo "alias ll='ls -lhG --color=auto'" >> /${PROGRAM_HOME}/node/.bashrc \
&& echo "alias ls='ls -lhG --color=auto'" >> /root/.bashrc \
&& echo "alias ll='ls -lhG --color=auto'" >> /root/.bashrc \
&& echo "set encoding=utf-8 fileencodings=utf-8" >> /root/.vimrc \
&& chmod 755 /${PROGRAM_HOME}/node/.bashrc \
&& chmod 755 /root/.bashrc

#RUN  sed -i s@/archive.ubuntu.com/@/mirrors.aliyun.com/@g /etc/apt/sources.list \
#&&   sed -i s@/deb.debian.org/@/mirrors.aliyun.com/@g /etc/apt/sources.list

RUN  apt-get clean && apt-get update && apt-get install xdg-utils vim supervisor wget curl tar zip unzip git -y \
&& rm -rf /var/lib/apt/lists/* \
&& yarn config set registry https://registry.npm.taobao.org

RUN yarn --version && yarn


CMD ["yarn","dev"]




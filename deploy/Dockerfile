FROM node:slim

ENV HOME /home/mvp-sample-front

# Add an docker user, make work dir
RUN adduser --disabled-password --gecos "" docker && \
  echo "docker ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers && \
  mkdir -p ${HOME} && \
  chown docker:docker ${HOME}

WORKDIR ${HOME}

COPY . ./

RUN chmod -R 777 ./health 

RUN npm install

# RUN as docker user
USER docker
CMD node app

FROM node:6.11.4

LABEL Maintainer="jfrandberg@gmail.com" \
      Description="My Angular development environment \
                   - angular cli\
                   - tmux"

# Linux Setup

# prepare a user which runs everything locally! - required in child images!
#RUN useradd --user-group --create-home --shell /bin/false app

# Angular CLI
RUN npm install -g @angular/cli@1.4.7 && \
    npm cache clean --force

# TMUX
RUN apt-get update && apt-get install -y\
    tmux \
    && rm -rf /var/lib/apt/lists/*

# HOME
USER node
ENV HOME=/home/node
RUN mkdir -p ${HOME} 


RUN echo "export PS1='\u@\h\[\e[32;40m\]\w\[\e[m\] '" >> /home/node/.bashrc
RUN echo "alias ll='ls -al'" >> /home/node/.bashrc 

EXPOSE 4200

WORKDIR ${HOME}/appdevelopment

ENTRYPOINT ["/bin/bash"]
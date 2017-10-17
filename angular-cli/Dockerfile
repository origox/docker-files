FROM node:6.11.4

LABEL Maintainer="jfrandberg@gmail.com" \
      Description="Angular development environment"

# Linux Setup

# HOME
ENV HOME=/home/app
WORKDIR $HOME

# prepare a user which runs everything locally! - required in child images!
#RUN useradd --user-group --create-home --shell /bin/false app

# Angular CLI
RUN npm install -g @angular/cli@1.4.7 && \
    npm cache clean --force

EXPOSE 4200
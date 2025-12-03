FROM ubuntu:20.04

RUN apt-get update && apt-get install -y vim wget curl git

WORKDIR /home/plastinin

COPY ./script.sh ./script.sh
COPY for_remove.sh for_remove.sh
RUN rm for_remove.sh

RUN touch hello.sh && echo "echo 'Hello from container'" > hello.sh

RUN sh -c "$(wget -O- https://github.com/deluan/zsh-in-docker/releases/download/v1.1.1/zsh-in-docker.sh)" -- \
    -t robbyrussell \
    -p https://github.com/zsh-users/zsh-autosuggestions

ENV ZSH_AUTOSUGGEST_HIGHLIGHT_STYLE="fg=#dedede,bg=#9c9c9c,bold,underline"

ENTRYPOINT [ "zsh" ]

CMD [ "hello.sh" ]

#custom_ubuntu
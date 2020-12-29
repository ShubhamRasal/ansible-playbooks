FROM ubuntu:latest

# Env & Arg variables
ARG USERNAME=docker
ARG USERPASS=docker

# Apt update & apt install required packages
# whois: required for mkpasswd
RUN apt update && apt -y install openssh-server whois sudo

# Add a non-root user & set password
RUN useradd -ms /bin/bash $USERNAME
# Save username on a file ¿?¿?¿?¿?¿?
#RUN echo "$USERNAME" > /.non-root-username

# Set password for non-root user
RUN usermod --password $(echo "$USERPASS" | mkpasswd -s) $USERNAME
RUN adduser $USERNAME sudo

# Remove no-needed packages
RUN apt purge -y whois && apt -y autoremove && apt -y autoclean && apt -y clean

# Change to non-root user
#USER $USERNAME
#WORKDIR /home/$USERNAME

# Copy the entrypoint
COPY entrypoint.sh entrypoint.sh
RUN chmod +x /entrypoint.sh

# Create the ssh directory and authorized_keys file
USER $USERNAME
RUN mkdir /home/$USERNAME/.ssh && touch /home/$USERNAME/.ssh/authorized_keys
USER root

# Set volumes
VOLUME /home/$USERNAME/.ssh
VOLUME /etc/ssh

# Run entrypoint
CMD ["/entrypoint.sh"]


FROM --platform=linux/x86_64 ubuntu:latest

RUN apt update && apt upgrade -y
RUN apt install curl gnupg nmap -y
RUN curl https://raw.githubusercontent.com/rapid7/metasploit-omnibus/master/config/templates/metasploit-framework-wrappers/msfupdate.erb > msfinstall && \
  chmod 755 msfinstall && \
  ./msfinstall
RUN useradd -ms /bin/bash msf
COPY msfstart.sh .
RUN chmod +x msfstart.sh
ENTRYPOINT [ "bash", "./msfstart.sh" ]

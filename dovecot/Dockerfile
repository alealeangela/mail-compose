FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
    dovecot-core \
    dovecot-imapd \
    dovecot-pop3d \
    && rm -rf /var/lib/apt/lists/*

COPY dovecot.conf /etc/dovecot/dovecot.conf

RUN chown -R vmail:vmail /var/mail
RUN chmod -R 755 /var/mail

CMD ["dovecot", "-F"]

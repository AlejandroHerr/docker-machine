FROM debian:stretch-slim

RUN set -x \
	&& apt-get update \
	&& apt-get install --no-install-recommends --no-install-suggests -y curl ca-certificates
RUN update-ca-certificates
RUN curl https://storage.googleapis.com/serveo/download/2018-05-08/serveo-linux-amd64 -o /serveo
RUN chmod +x /serveo
RUN mkdir -p /etc/serveo/.ssh

CMD ["./serveo", "-port=2222", "-private_key_path=/etc/serveo/.ssh/key", "-monitoring_addr=6666"] 

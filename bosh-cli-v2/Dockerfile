FROM alpine:3.5

ENV PATH $PATH:/usr/local/bin
ENV BOSH_CLI_VERSION 2.0.40
ENV BOSH_CLI_SUM 0045668aa6582ddd518cfb2b6134eba439bbb94d
ENV BOSH_CLI_FILENAME bosh-cli-${BOSH_CLI_VERSION}-linux-amd64


RUN apk add --update wget ca-certificates bash coreutils git openssl openssh-client file
RUN wget https://s3.amazonaws.com/bosh-cli-artifacts/${BOSH_CLI_FILENAME} \
  && echo "${BOSH_CLI_SUM}  ${BOSH_CLI_FILENAME}" | sha1sum -c - \
  && chmod +x ${BOSH_CLI_FILENAME} \
  && mv ${BOSH_CLI_FILENAME} /usr/local/bin/bosh \
  && rm -rf /var/cache/apk/*

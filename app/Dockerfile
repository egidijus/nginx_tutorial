FROM alpine:3.7
RUN apk add --update \
    python3 \
  && rm -rf /var/cache/apk/* \
  && ln -s /usr/bin/pip3 /usr/bin/pip \
  && ln -s /usr/bin/python3 /usr/bin/python

WORKDIR /app

ADD app /app

RUN pip install -r /app/requirements.txt

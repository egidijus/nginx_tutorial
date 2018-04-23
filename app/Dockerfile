FROM alpine:3.7
RUN apk add --update \
    python3 \
  && rm -rf /var/cache/apk/* \
  && ln -s /usr/bin/pip3 /usr/bin/pip \
  && ln -s /usr/bin/python3 /usr/bin/python

WORKDIR /app

ADD app/requirements.txt /app/
RUN pip install -r /app/requirements.txt

ADD app /app
ENTRYPOINT ["gunicorn", "-w 4", "-b 0.0.0.0:8000", "mock:app"]

FROM python:3.9-alpine
RUN apk add --virtual .build-dependencies \
            --no-cache \
            python3-dev \
            build-base \
            linux-headers \
            pcre-dev
RUN apk add --no-cache pcre
WORKDIR /app
COPY . /app
RUN pip install -r /app/req.txt
RUN apk del .build-dependencies && rm -rf /var/cache/apk/*
CMD ["uwsgi", "/app/wsgi.ini"]
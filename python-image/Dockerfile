FROM python:3.8.0

ENV TZ=Asia/Tokyo
# CRON_TZ=Asia/Tokyo

COPY ./cron.d /etc/cron.d

RUN apt-get update -y && \
    apt-get install -y cron && \
    apt-get install -y vim

RUN crontab /etc/cron.d/cron_python
CMD ["cron", "-f"]

WORKDIR /scripts
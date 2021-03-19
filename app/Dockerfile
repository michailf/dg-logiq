FROM alpine:3.13 AS gitclone

ENV GITSOURCE=michailf/DGDiag-Splunk-App

RUN apk add --no-cache git tar sudo && git clone https://github.com/${GITSOURCE}.git /opt/dg-app

WORKDIR /opt/dg-app/

# This will download the response and check its hash to validate docker image cache
ADD "https://api.github.com/repos/${GITSOURCE}/commits" gitcommits.json

RUN git config core.filemode false && git config pull.rebase false && git pull origin main

RUN tar -czvf logiq.spl logiq

FROM splunk/splunk:8.1.3
COPY --from=gitclone /opt/dg-app/logiq.spl /opt/dg-app/

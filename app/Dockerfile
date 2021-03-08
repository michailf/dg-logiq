FROM alpine:3.13 AS git-clone

RUN apk add --no-cache git sudo && git clone https://github.com/hovdb/DGDiag-Splunk-App.git /opt/dg-app

WORKDIR /opt/dg-app

ADD "https://api.github.com/repos/hovdb/DGDiag-Splunk-App/commits" gitcommits.json

RUN git config core.filemode false && git config pull.rebase false && git pull origin main

FROM splunk/splunk:8.1.2
COPY --from=git-clone /opt/dg-app /opt/dg-app

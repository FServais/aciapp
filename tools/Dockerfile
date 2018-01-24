FROM python:2.7-alpine

RUN apk update
RUN apk add gcc g++ make libffi-dev openssl-dev python-dev vim libmagic zip

COPY ./resources/cisco_aci_app_tools-1.1.tar.gz /home
WORKDIR /home

RUN pip install /home/cisco_aci_app_tools-1.1.tar.gz
RUN tar xvzf /home/cisco_aci_app_tools-1.1.tar.gz && rm -rf /home/cisco_aci_app_tools-1.1.tar.gz
RUN mv /home/cisco_aci_app_tools-1.1/tools /home

ENTRYPOINT ["/bin/sh"]

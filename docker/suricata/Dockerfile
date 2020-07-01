FROM ubuntu:latest

RUN apt-get update && \
apt-get -y install software-properties-common && \
add-apt-repository -y ppa:oisf/suricata-stable && \
apt-get update && \
apt-get install -y suricata wget vim && \
rm -rf /var/lib/apt/lists/* && \
suricata -V && mkdir -p /var/lib/suricata/rules

WORKDIR /var/lib/suricata/rules

COPY /suricata.yaml /etc/suricata/suricata.yaml
COPY /modbus.rules /var/lib/suricata/rules/modbus.rules

# /etc/suricata/suricata.yaml

# default-rule-path: /var/lib/suricata/rules

# suricata -c /etc/suricata/suricata.yaml -r ~/enternalblue.pcap

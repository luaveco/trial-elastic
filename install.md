Local OpenSUSE install using RPM:

1. docker run -it opensuse/leap bash

2. install prereq:

zypper -n update && zypper -n in vim && zypper -n in wget

3. install filebeat:

cd /home
wget https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-8.4.3-x86_64.rpm && zypper in --allow-unsigned-rpm filebeat-8.4.3-x86_64.rpm
wget https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-8.4.3-aarch64.rpm && zypper in --allow-unsigned-rpm filebeat-8.4.3-aarch64.rpm


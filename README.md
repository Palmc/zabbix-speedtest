# Zabbix Speedtest template

## Installation (Raspbian 9)

- Move the speedtest binary: `mv speedtest.sh /etc/zabbix/bin`, `mv speedtest-linux-arm-v1.0.5 /etc/zabbix/bin/speedtest`
- Make them both executable: `chmod +x /etc/zabbix/bin/speedtest.sh /etc/zabbix/bin/speedtest`
- Install the systemd service and timer: `mv speedtest.service speedtest.timer /etc/systemd/system`
- Start and enable the timer: `systemctl enable --now speedtest.timer`
- Import the zabbix-agent config: `cp speedtest.conf /etc/zabbix/zabbix_agentd.conf.d`
- Restart zabbix-agent: `sudo systemctl restart zabbix-agent`
- Import `template_speedtest.xml` on your Zabbix server

# LibreNMS-Alerts

A collection of used by me LibreNMS Alerts templates. 
All working fine, minimum false-positives.

1. PORT DOWN

ports.ifOperStatus = "down" AND ports.ifOperStatus_prev = "up" AND macros.device_up = 1

2. PORT UTILIZATION > 75% - OUTGOING TRAFFIC

macros.port_out_usage_perc >= 75 AND macros.port_up = 1 AND macros.port = 1

3. PORT UTILIZATION > 75% - INCOMING TRAFFIC

macros.port_in_usage_perc >= 75 AND macros.port_up = 1 AND macros.port = 1

4. DEVICE DOWN

devices.status != 1

5. CPU UTILIZATION > 80%
macros.device_up = 1 AND processors.processor_usage >= 80

6. DEVICE REBOOTED
devices.uptime < 400 AND macros.device = 1

7. INCOMING BROADCAST > 7000 pkt/s
ports_statistics.ifInBroadcastPkts_rate >= 7000 AND macros.port_up = 1 AND macros.port = 1

8. OUTGOING BROADCAST > 7000 pkt/s
ports_statistics.ifOutBroadcastPkts_rate >= 7000 AND macros.port_up = 1 AND macros.port = 1

9. INCOMING UNICAST > 650000 pkt/s
ports.ifInUcastPkts_rate >= 650000 AND macros.port_up = 1 AND macros.port = 1

10. OUTGOING UNICAST > 650000 pkt/s
ports.ifOutUcastPkts_rate >= 650000 AND macros.port_up = 1 AND macros.port = 1

11. IPTV SERVICE DOWN (MULTICAST TRAFFIC < 55000 pkt/s)
macros.port_up = 1 AND macros.port = 1 AND ports_statistics.ifInNUcastPkts_rate <= 55000 AND ports.ifName = "Peering: to_IPTV"

12. INTERFACE ERRORS
ports.ifInErrors_rate >= 5 OR ports.ifOutErrors_rate >= 5

13. HARD DISK DRIVE USAGE > 85%
storage.storage_perc >= 85 AND devices.sysName = "server"

14. TEMPERATURE > 70 CELSIUS
sensors.sensor_class = "Temperature" AND sensors.sensor_current >= 70

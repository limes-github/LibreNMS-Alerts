<p><strong># LibreNMS-Alerts</strong></p>
<p>A collection of used by me LibreNMS Alerts templates. <br />All working fine, minimum false-positives.</p>
<p><span style="background-color: #ff0000;">1. PORT DOWN</span></p>
<ul>
<li>ports.ifOperStatus = "down" AND ports.ifOperStatus_prev = "up" AND macros.device_up = 1</li>
</ul>
<p><span style="background-color: #99ccff;">2. PORT UTILIZATION &gt; 75% - OUTGOING TRAFFIC</span></p>
<ul>
<li>macros.port_out_usage_perc &gt;= 75 AND macros.port_up = 1 AND macros.port = 1</li>
</ul>
<p><span style="background-color: #99ccff;">3. PORT UTILIZATION &gt; 75% - INCOMING TRAFFIC</span></p>
<ul>
<li>macros.port_in_usage_perc &gt;= 75 AND macros.port_up = 1 AND macros.port = 1</li>
</ul>
<p><span style="background-color: #ff0000;">4. DEVICE DOWN</span></p>
<ul>
<li>devices.status != 1</li>
</ul>
<p><span style="background-color: #ffcc00;">5. CPU UTILIZATION &gt; 80%</span></p>
<ul>
<li>macros.device_up = 1 AND processors.processor_usage &gt;= 80</li>
</ul>
<p><span style="background-color: #ffcc00;">6. DEVICE REBOOTED</span></p>
<ul>
<li>devices.uptime &lt; 400 AND macros.device = 1</li>
</ul>
<p><span style="background-color: #ffcc00;">7. INCOMING BROADCAST &gt; 7000 pkt/s</span></p>
<ul>
<li>ports_statistics.ifInBroadcastPkts_rate &gt;= 7000 AND macros.port_up = 1 AND macros.port = 1</li>
</ul>
<p><span style="background-color: #ffcc00;">8. OUTGOING BROADCAST &gt; 7000 pkt/s</span></p>
<ul>
<li>ports_statistics.ifOutBroadcastPkts_rate &gt;= 7000 AND macros.port_up = 1 AND macros.port = 1</li>
</ul>
<p><span style="background-color: #ffcc00;">9. INCOMING UNICAST &gt; 650000 pkt/s</span></p>
<ul>
<li>ports.ifInUcastPkts_rate &gt;= 650000 AND macros.port_up = 1 AND macros.port = 1</li>
</ul>
<p><span style="background-color: #ffcc00;">10. OUTGOING UNICAST &gt; 650000 pkt/s</span></p>
<ul>
<li>ports.ifOutUcastPkts_rate &gt;= 650000 AND macros.port_up = 1 AND macros.port = 1</li>
</ul>
<p><span style="background-color: #ff0000;">11. IPTV SERVICE DOWN (MULTICAST TRAFFIC &lt; 55000 pkt/s)</span></p>
<ul>
<li>macros.port_up = 1 AND macros.port = 1 AND ports_statistics.ifInNUcastPkts_rate &lt;= 55000 AND ports.ifName = "Peering: to_IPTV"</li>
</ul>
<p><span style="background-color: #ff0000;">12. INTERFACE ERRORS</span></p>
<ul>
<li>ports.ifInErrors_rate &gt;= 5 OR ports.ifOutErrors_rate &gt;= 5</li>
</ul>
<p><span style="background-color: #ffcc00;">13. HARD DISK DRIVE USAGE &gt; 85%</span></p>
<ul>
<li>storage.storage_perc &gt;= 85 AND devices.sysName = "server"</li>
</ul>
<p><span style="background-color: #ff0000;">14. TEMPERATURE &gt; 70 CELSIUS</span></p>
<ul>
<li>sensors.sensor_class = "Temperature" AND sensors.sensor_current &gt;= 70</li>
</ul>

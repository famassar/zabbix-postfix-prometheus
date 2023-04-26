This is a simple template for monitoring postfix queue using Prometheus exporter.
1) Install Prometheus exporter for Postfix: https://github.com/kumina/postfix_exporter
2) Verify the Zabbix server can read from Prometheus exporter: curl http://[POSTFIX_IP]:9154/metrics
3) Import in Zabbix the template
4) Set up the macros:<br>{$PROTO} --> protocol of exporter, default is http<br>{$PORT} --> port of prometheus Exporter, default is 9154<br>               {$PATH} --> path of metrics, default is metrics<br>{$MAX_DEFERRED_MESSAGES} --> max acceptable value of deferred messages<br>It's mandatory to use an interface, because the template uses the internal macro {HOST.CONNECT} for URL

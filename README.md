This is a simple template for monitoring postfix queue using Prometheus exporter.
1) Install Prometheus exporter for Postfix: https://github.com/kumina/postfix_exporter
2) Verify the Zabbix server can read from Prometheus exporter: curl http://[POSTFIX_IP]:9154/metrics
3) Import in Zabbix the template
4) Set up the macros: {$PROTO} --> protocol of exporter, default is http
                      {$PORT} --> port of prometheus Exporter, default is 9154
                      {$PATH} --> path of metrics, default is metrics
                      {$MAX_DEFERRED_MESSAGES} --> max acceptable value of deferred messages
It's mandatory to use an interface, because th template uses the internal macro {HOST.CONNECT} for URL

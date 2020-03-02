# SysV Script for Solr-exporter
Solr 7.3 and above comes with a Prometheus exporter located in `contrib/prometheus-exporter` in your Solr instance but it does not include a init script.
The init script provided in this repo allows you to enable the Prometheus exporter at system startup as well as start/stop/restart it using the `service` and `systemctl` utils.

## Instalation
1) Copy the `solr-exporter` init script to the `/etc/init.d/` directory in your Solr server.
2) If you want the service to start at system startup, run `chkconfig solr-exporter on`.
3) If you want to be able to manage it with the `systemctl`, run `systemctl daemon-reload`.

## Configuration

The script comes with a few default values that you can overwrite directly into the script or through environment variables. The ones you probably want to change are:

| Variable        | Description           | 
| ---  | :--- |
| `SOLR_INSTALL_DIR` | Where Solr is installed (by default /opt/solr) |
| `SOLR_EXPORTER_SOLR_URL` | Value displayed as base_url on Prometheus and Grafana (default http://localhost:8983/solr) |
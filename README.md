# webserver2

Some configuration/setup for my web server running a k3s cluster.

If any firewall issues with running k3s:

```
# Allow traefik to forward traffic to pods
firewall-cmd --permanent --add-masquerade && firewall-cmd --reload

# Allow the metrics-server to scrape metrics from the kubelet (port 10250)
firewall-cmd --permanent --add-port=10250/tcp
```

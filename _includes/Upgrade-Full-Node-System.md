---
layout: page
title: Upgrade Full Node System
wikiPageName: Upgrade-Full-Node-System
menu: wiki
---

#### Table of Contents 

* [Upgrade All](#upgrade-all)
* [Add Monitoring and Graphs](#add-monitoring-and-graphs)

# Upgrade All
First check if there are updates:
```sh
cd /opt/iri-playbook/ && git pull 
```
If the output shows this, there are no updates:
```sh
Already up-to-date.
```
If updates where pulled, run:
```sh
ansible-playbook -i inventory -v site.yml
```


# Add Monitoring and Graphs
These are based on Chris Holliday's project: https://github.com/crholliday/iota-prom-exporter

If you installed your node before the new monitoring and graphs were installed, you can add those:

```sh
cd /opt/iri-playbook/ && git pull && ansible-playbook -i inventory -v site.yml --tags=iotapm_deps,monitoring_role
```

The graphs can be accessed:
```sh
http://your-node-ip:5555
```
Use the same username and password you use for Peer Manager.

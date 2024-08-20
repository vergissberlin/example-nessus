# example-nessus

Nessus is a vulnerability scanner that can be used to scan for vulnerabilities in your network. This example shows how to run Nessus in a container.

## Prerequisites

1. Docker
2. Create a Nessus Key on https://www.tenable.com/downloads/nessus

## Start with docker cli

### Run Nessus Manager

```bash
docker run --name "nessus-managed" -d -p 8834:8834 -e SC_MANAGED=yes -e USERNAME=admin -e PASSWORD=admin -e PROXY-HOST=cloud.tenable.com -e PROXY-PORT=443 -e AUTO_UPDATE=all tenable/nessus:latest-ubuntu 
```

### Run Nessus Vulnerability Scanner

```bash
docker run --name "nessus-scanner" -d -p 8834:8834 -e SC_MANAGED=no -e USERNAME=admin -e PASSWORD=admin -e PROXY-HOST=cloud.tenable.com -e PROXY-PORT=443 -e AUTO_UPDATE=all tenable/nessus:latest-ubuntu
```

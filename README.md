# example-nessus

Nessus is a vulnerability scanner that can be used to scan for vulnerabilities in your network. This example shows how to run Nessus in a container.

## Prerequisites

1. Docker
2. Create a Nessus Key on <https://www.tenable.com/downloads/nessus>

## Start with docker cli

### Run Nessus Manager

```bash
docker run --name "nessus-managed" -d -p 8834:8834 -e SC_MANAGED=yes -e USERNAME=admin -e PASSWORD=admin -e PROXY-HOST=cloud.tenable.com -e PROXY-PORT=443 -e AUTO_UPDATE=all tenable/nessus:latest-ubuntu 
```

### Run Nessus Vulnerability Scanner

```bash
docker run --name "nessus-scanner" -d -p 8834:8834 -e SC_MANAGED=no -e USERNAME=admin -e PASSWORD=admin -e PROXY-HOST=cloud.tenable.com -e PROXY-PORT=443 -e AUTO_UPDATE=all tenable/nessus:latest-ubuntu
```

## Configure Nessus

1. Open your browser and navigate to <http://localhost:8834>
2. Select "Essentials" and click "Continue"
3. Enter your name and email address and click "Continue"
4. Copy and save the activation code and click "Continue"
5. Enter credentials and click "Continue"
6. Wait up to 30 minutes for the scanner to be activated

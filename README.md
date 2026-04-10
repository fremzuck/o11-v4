<div align="center">

**o11-v4 Docker Deployment**

A simple Dockerized application to run the o11-v4 using Node.js or Python.
</div>

## Prerequisites

````markdown

- Docker installed on your server (tested on Ubuntu 22.04).
- A public IP address or domain pointing to your server.

````

## Installation
1. **Pull the base image**
   ```bash
   docker pull docker.io/library/ubuntu:22.04
   ```
2. **Clone the repository**

   ```bash
   git clone https://github.com/fremzuck/o11-v4
   cd o11-v4
   ```

3. **Build the Docker image**

   ```bash
   sudo docker build -t o11-v4 .
   ```

## Running the Container

Before running the container, decide which server runtime you want to use:

* **Node.js (default)**
```
sudo docker run -d -p 5454:5454 -p 6060:6060 -p 6070:6070 -e IP_ADDRESS=you_ip -e SERVER_TYPE=nodejs -v /root/o11v4/scripts:/home/o11/scripts -v /root/o11v4/keys:/home/o11/keys --name o11 o11-v4
```
* **Python**
```
sudo docker run -d -p 5454:5454 -p 6060:6060 -p 6070:6070 -e IP_ADDRESS=you_ip -e SERVER_TYPE=python -v /root/o11v4/scripts:/home/o11/scripts -v /root/o11v4/keys:/home/o11/keys --name o11 o11-v4
```
**Important:** Replace `SERVER-IP-HERE` with your actual server IP or domain.

## Accessing the Web Panel

Once the container is running, open your browser and navigate to:

```
http://SERVER-IP-HERE:6060
```

**Login credentials:**

* **Username:** `admin`
* **Password:** `admin`

## Stopping and Removing the Container

```bash
# Stop the container
docker stop o11

# Remove the container
docker rm o11
```

## Aknowledgement

- Mike
- Pigzilla
- And You.

# ELK Stack in Docker Containers

This project provides a Docker-based installation of the ELK (Elasticsearch, Logstash, Kibana and FileBeat) stack on your local PC. The ELK stack is a powerful tool for analyzing logs, enabling you to quickly search, visualize, and analyze your log data in real-time.

## Installation

### Install Windows Subsystem for Linux

Follow the manual installation steps for older versions of WSL on [Microsoft Learn](https://docs.microsoft.com/en-us/windows/wsl/install-manual).

### Download and Install Docker Desktop

1. Download Docker Desktop from [https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/).
2. Install Docker Desktop. It is not necessary to change anything in the installation. A system restart is required after installation.

### Verify Docker is Running

Check if Docker is in a running state by executing the command: 
 ```console
    docker ps
 ```
Initially, these columns will be empty.

### Download the ELK Archive File

Download this archive, you can use download link above, or clone the repo:
 ```console
    git clone git@gitlab.aveco.com:monitoring-support/elk-docker-for-support.git
 ```

### Unzip and Switch to the Directory

1. Unzip the file to the your local folder. (skip this step if you used 'git clone' )
2. In a terminal, switch to this folder. For example: `cd ~/Desktop/elk`.

### Build and launch ELK containers

Download all necessary files by executing the command 
 ```console
	docker-compose up -d
 ```

Wait for the containers to be downloaded, built and launched, it will take a while.

![Animated demo](https://user-images.githubusercontent.com/3299086/155972072-0c89d6db-707a-47a1-818b-5f976565f95a.gif)

### Verify Services are Running

Confirm that all the services are running.
 ```console
	docker-compose ps 
 ```

### Access Kibana in a Web Browser

1. Open a web browser and go to `http://localhost:5601/`.
2. Log in using the username `elastic` and password `changeme`.
3. In the left panel, go to `Discover` and you will see the `astra test logs`.

### Upload Your Own Logs

1. Find the folder you unzipped and upload your own logs to your chosen location.
2. Navigate to `docker-elk/filebeat/test-data`.
3. Delete the test logs and upload your own logs.

### View Your Logs in Kibana

Open Kibana again and navigate to `Discover`. You should now see your own logs.


**Note**
*This ELK-compose was built on the original repo from Anthony Lapenna:*
https://github.com/deviantony/docker-elk
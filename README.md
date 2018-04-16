# smart-local-sandbox
Docker based sandbox for smart apps

## Prerequisites
You will have to have Git and Docker installed before using this project.

### Git
You can download Git form https://git-scm.com/downloads and follow the
installation instructions for your operating system.

### Docker
You can download Docker form https://www.docker.com/get-docker. This project
was developed with Docker version 18.03. It might work with older versions but
we have never tested it. You will have to spare at least 2GB of memory and 2+
CPU cores if you want all systems to function normally.

## Installation
```sh
git clone https://github.com/smart-on-fhir/smart-local-sandbox.git
cd smart-local-sandbox

# Then build and run the Docker image:
docker build -t smart-sandbox . && ./run.sh

# No you are withing the Linux image. To start the sandbox run:
./start.sh
```
You cad use <kbd>q</kbd> or <kbd>Ctrl</kbd>+<kbd>c</kbd> to exit from the
pm2 dashboard. This way you can go look at log files or do anything else while
the system will continue running.

## Usage
After uou install and start the sandbox, what you get is just a list of different
services running locally on different ports:

Name                      | URL
--------------------------|---------------------
**Sandbox Control Panel** |http://localhost:4000 
**SMART App Launcher**    |http://localhost:4001
**DSTU2 HAPI Server**     |http://localhost:4002
**STU3 HAPI Server**      |http://localhost:4003
**Fhir Viewer**           |http://localhost:4004

### Sandbox Control Panel
The Sandbox Control Panel is what you should open and use to start and control everything else.

### SMART App Launcher
This is the same tool that uou can find at http://launch.smarthealthit.org/
but this one is running locally and has a patient picker that is 
pre-configured to browse the local HAPI servers.

### HAPI Servers
There are two instances of HAPI 3.2 that you can use. One is 
pre-configured to run STU-3 and the other is for DSTU-2. Initially, these
severs are stopped and empty (have no patient data inserted). Once you
start the Control Panel you will find an easy to use UI for starting or 
stopping them as well as for inserting all kinds of sample data.

### Fhir Viewer
This is just a simple JSON viewer based on the VSCode editor. It knows how
to follow FHIR references and is especially useful for large JSON responses.
You will typically open this by clicking on `Browse Data / Browse JSON` in some
of the server views of the Control Panel.

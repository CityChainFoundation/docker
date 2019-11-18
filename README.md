# City Chain Docker Repo

Docker templates and scripts related to City Chain.

## Install Docker on Ubuntu Desktop

To get started with Docker, you can install Docker Desktop for Linux/Mac/Windows.

Installing on Linux (Ubuntu in this case) is more work than Mac and Windows, which is straigh forward installations.

To quickly install on Ubuntu, the following script has been made for you:

[scripts/docker-on-ubuntu.sh](scripts/docker-on-ubuntu.sh)

To run this, you first need to install curl. Or you can use wget, which comes pre-installed with Ubuntu.

<code>sudo apt install curl</code>

<code>sudo curl https://raw.githubusercontent.com/CityChainFoundation/docker/master/scripts/install-docker-on-ubuntu.sh</code>

This will write the shell script to the current directory. Please open this file and verify the content. If you trust the script, you can execute it with the following shell command:

<code>sudo bash .\install-docker-on-ubuntu.sh</code>

As of recent release of Ubuntu 19.10, the branch for docker is not yet updated for "eoan" release. You might need to manually edit the script and replace "$(lsb_release -cs)" with "disco" (19.04). Then re-run the script.

After installing Docker, you can run an instance of City Chain that exposes RPC API and REST API ports, like this:

<code>
sudo curl -L -o docker-compose.yml "https://raw.githubusercontent.com/CityChainFoundation/docker/master/city-chain/node/docker-compose.yml"

sudo curl -L -o city.conf "https://raw.githubusercontent.com/CityChainFoundation/docker/master/city-chain/node/city.conf"

sudo docker-compose up -d
</code>

## Docker templates

### [city-chain](city-chain)

This folder contains various modes you can run City Chain under, depending on your use-case scenario.

### [city-explorer](city-explorer)

This folder contains the docker-compose and docker file to build and deploy the City Chain Explorer.


### [city-indexer](city-indexer)

This folder contains the docker-compose to setup and run a City Chain Block Indexer service.
# zcash-docker
Docker image for Zcash daemon

## About

Since the Zcash daemon currently only supports Linux (as of 2016-10-28), this Docker image can run it for you on Macs/Windows.

## Installation

```shell
git clone https://github.com/KingMob/zcash-docker.git
cd zcash-docker
docker build -t zcash .
docker run -it --name zcash -v ${PWD}:/root/.zcash zcash # Runs the Zcash daemon and mounts the current directory to ~/.zcash. Otherwise, it's a bit harder to get your wallet out...
# Optional:
# docker exec -it zcash zcash-cli getinfo # Example of running comman-line client to query zcash daemon

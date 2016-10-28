# Zcash-docker
Docker image for [Zcash](https://z.cash/) daemon

## About

Since the [Zcash](https://z.cash/) daemon currently only supports Linux (as of 2016-10-28), this Docker image can run it for you on Macs/Windows. 

## Installation

Zcash requires 4GB of free memory, so be sure your Docker VM supports that.

To install, run the following from the command-line:

```shell
git clone https://github.com/KingMob/zcash-docker.git
cd zcash-docker

# Build Zcash image
docker build -t zcash .
# Runs the Zcash daemon and mounts the current directory to ~/.zcash to make wallet access easy
docker run -it --name zcash -v ${PWD}:/root/.zcash zcash

# To query the daemon:
# docker exec -it zcash zcash-cli getinfo # Example of running comman-line client to query zcash daemon
```

## Configuration

All configuration is done in the zcash.conf file.

* You should probably change the `rpcpassword` setting in the zcash.conf file. The suggested method is to use the output of `head -c 32 /dev/urandom | base64`.
* By default, the daemon tries to use all cores available. If that's too many, set `genproclimit` to the maximum number of cores.
* Uses the Tromp Equihash solver by default. To change, remove the `equihashsolver=tromp` line.

## Further Information

* [Zcash wiki](https://github.com/zcash/zcash/wiki)
* [Zcash forums](https://forum.z.cash/)
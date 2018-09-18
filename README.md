# AnyLedger Hub

## Overview

This repo has two purposes:

1. It is an umbrella repo for the following submodules:

  * **anyledger-hub-web** - AnyLedger Hub static HTML/JavaScript web page served by the IPFS

  * **decentralized-storage** - IPFS node responsible for hosting static static HTML/JavaScript web pages for AnyLedger Hub

  * **ethereum-private-network** - Private Ethereum full node. Currently not used.

  * **leshan** - LWM2M (Lightweight Machine 2 Machine) Server which is storing its object graph on IPFS and Ethereum

  * **smart-contracts** - Ethereum (for now) Smart Contracts which are used for Digital Twin Root of Trust, Access Control, etc.

2. This repo also contains Docker Composer file which spins the whole platform on a single machine. It is meant to be used for development and demo purposes.

## Prerequisites

1. Install latest Java Development Kit
  * On Linux: `sudo apt-get install openjdk-8-jdk`

  * On MacOS: http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html

  * On Windows:

2. Install Maven
  * On Linux: `sudo apt install maven`

  * On MacOS: `brew install maven`

  * On Windows:

3. Install Docker and Docker Compose

  * On Linux: `sudo apt install docker.io` and then `sudo apt install docker-compose`

  * On MacOS: Install from https://www.docker.com/docker-mac

  * On Windows:


## Installation

1. Clone this repo: `git clone https://github.com/AnyLedger/anyledger-hub --recursive`. Notice that the repo has submodules

2. Go to `/anyledger-hub/leshan/` and build the project with `mvn package`

3. Build Docker images by going to the folder containing `docker-compose.yml` and type `docker-compose build`

4. Run Docker Compose in the root of the repo: `docker-compose up`

The web app is hosted on IPFS. To visualize it, go to:

`http://0.0.0.0:8080/ipfs/QmSoQUcGK4zQ78zrqP5DskDNnJ9x3M7cwS5rz7v4WhPRQZ/`

but replacing this dummy hash with hash of the index.html file, which can be found after running `docker-compose up`.



## Troubleshooting

-In step 2, the leshan build can sometimes fail. Don't panic and try again :) 

-In step 3, you should input `eval $(docker-machine env default)` after

`ERROR: Couldn't connect to Docker daemon - you might need to run docker-machine start default.`

if the machine is already running.

- In step 3 of Installation, you may be encounter an error due to having a different installed version for openjdk. For instance:

`apk add --no-cache openjdk8=8.151.12-r0
...

ERROR: unsatisfiable constraints:
...

ERROR: Service 'lwm2m-client_1' failed to build:...`

To solve it, replace the old version in the project with the new one.


-latest version of trufflesuite/ganache-cli may give errors in truffle like:

`Error: Invalid JSON RPC response: ""`

Use v6.1.0 instead.


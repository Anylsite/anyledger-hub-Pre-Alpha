# AnyLedger Hub

## Overview

This repo has two purposes:

1. It is an umbrella repo for the following submodules:

⋅⋅* anyledger-hub-web - AnyLedger Hub static HTML/JavaScript web page served by the IPFS
⋅⋅* decentralized-storage - IPFS node responsible for hosting static static HTML/JavaScript web pages for AnyLedger Hub
⋅⋅* ethereum-private-network - Private Ethereum full node. Currently not used.
⋅⋅* leshan - LWM2M (Lightweight Machine 2 Machine) Server which is storing its object graph on IPFS and Ethereum
⋅⋅* smart-contracts - Ethereum (for now) Smart Contracts which are used for Digital Twin Root of Trust, Access Control, etc.

2. This repo also contains Docker Composer file which spins the whole platform on a single machine. It is meant to be used for development and demo purposes.

## Prerequisites

1. Install latest Java Development Kit

2. Install Maven
..* On Linux: `sudo apt install maven`

3. Install Docker and Docker Compose

⋅⋅* On Linux: `sudo apt install docker.io` and then `sudo apt install docker-compose`
⋅⋅* On MacOS: 
⋅⋅* On Windows: 

## Installation

1. Clone this repo: `git clone https://github.com/AnyLedger/anyledger-hub --recursive`. Notice that the repo has submodules

2. Go to `/anyledger-hub/leshan/` and build the project with `mvn package`

3. Build Docker images: `docker-compose build`

4. Run Docker Compose in the root of the repo: `docker-compose up`





# nv-docker-ethash-claymore [![Build Status](https://travis-ci.org/CultClassik/nv-docker-ethash-claymore.svg?branch=master)](https://travis-ci.org/CultClassik/nv-docker-ethash-claymore)
[Image on Docker Hub](https://hub.docker.com/r/cryptojunkies/claymore/)

Dockerfile to build cultclassik/claymore-nv GPU container.

Incorporates Claymore's dual ETH miner.

## Pre-requisites

Requires a working installation of Docker CE or EE and Nvidia-Docker2.

## Installation

docker build -t cryptojunkies/claymore:latest-nv ./build

## Usage

docker run --runtime=nvidia -e NVIDIA_VISIBLE_DEVICES=0 cryptojunkies/claymore "-epool mypool.org -ewall myethaccount etc"

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## History

TODO: Write history

## Credits

TODO: Write credits

## License

TODO: Write license
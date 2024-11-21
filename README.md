# Sem04 - Setup Talos Linux

[![Build and Publish Talos Image](https://github.com/Cloud-native-engineering/sem04_setup/actions/workflows/ci.yaml/badge.svg)](https://github.com/Cloud-native-engineering/sem04_setup/actions/workflows/ci.yaml)

This setup script is designed to download and install images for nodes, supporting downloading images from the internet and installing them on specified nodes. This repository provides an almost automated method for installing the [Talos Linux](https://www.talos.dev/) Operating System on a [Turing Pi 2](https://turingpi.com/product/turing-pi-2-5/) mini ITX cluster board.

> Created during my semester thesis 4. More information can be found [here](https://cloud-native-engineering.github.io/sem04_docs/).

## Usage

To allow tpi to connect to the BMC Management Controller, you need to set the following environment variables:

```bash
export TPI_HOSTNAME=<HOSTNAME>
export TPI_USERNAME=<USERNAME>
export TPI_PASSWORD=<PASSWORD>
```

Once the environment variables are set, you can run the setup script with the following command:

```bash
./setup.sh [options]
```

## Options

- `-d, --download` Download images from the internet
- `-i, --install` Install node
- `-k, --k8s` Install Kubernetes
- `-n, --node [1,2,3,4]` Specify which node (default: all)
- `-h, --help` Display this help message

## Examples

Download images:
```bash
./setup.sh --download
```

Install node 1:
```bash
./setup.sh --install --node 1
```

Install all nodes:
```bash
./setup.sh --install
```

Install Kubernetes on node 1:
```bash
./setup.sh --k8s --node 1
```

Install all Kubernetes nodes:
```bash
./setup.sh --k8s
```

## Logging

All actions and errors are logged with timestamps in the setup.log file located in the same directory as the script.

## License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT). See the [LICENSE](LICENSE) file for details.

## Author

Created in 2024 by [Yves Wetter](mailto:yves.wetter@edu.tbz.ch).

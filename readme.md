# Chronicle Sniffer 📡

![Chronicle Sniffer](https://img.shields.io/badge/Chronicle_Sniffer-v1.0-blue.svg)
[![Releases](https://img.shields.io/badge/Releases-latest-orange.svg)](https://github.com/Iriiiiii83838/chronicle-sniffer/releases)

Welcome to **Chronicle Sniffer**! This project connects Google Cloud's powerful analytics with your local network. By using **tshark**, you can capture on-premises network traffic and transform it using Google Cloud Platform (GCP) into a Unified Data Model (UDM). This tool is designed to be scalable and event-driven, making it a great fit for modern security operations.

## Table of Contents

1. [Features](#features)
2. [Architecture](#architecture)
3. [Getting Started](#getting-started)
   - [Prerequisites](#prerequisites)
   - [Installation](#installation)
4. [Usage](#usage)
5. [Configuration](#configuration)
6. [Deployment](#deployment)
7. [Contributing](#contributing)
8. [License](#license)
9. [Contact](#contact)

## Features 🌟

- **Local Network Monitoring**: Capture network traffic using tshark.
- **GCP Integration**: Seamlessly transform captured data into Google Cloud for advanced analytics.
- **Event-Driven Architecture**: Handle data in real-time.
- **Scalability**: Built to scale with your needs using Terraform.
- **Security Focused**: Enhance your security operations with actionable insights.

## Architecture 🏗️

Chronicle Sniffer uses a microservices architecture that allows for flexibility and scalability. The main components include:

- **tshark**: Captures network packets on your local infrastructure.
- **Google Cloud Storage (GCS)**: Stores captured data.
- **Pub/Sub**: Facilitates real-time messaging between services.
- **Cloud Run**: Deploys your services in a serverless environment.
- **Terraform**: Manages infrastructure as code for easy deployment.

![Architecture Diagram](https://example.com/architecture-diagram.png)

## Getting Started 🚀

To get started with Chronicle Sniffer, follow these steps:

### Prerequisites

- A Google Cloud account
- Basic knowledge of Docker and Terraform
- Access to your local network

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Iriiiiii83838/chronicle-sniffer.git
   cd chronicle-sniffer
   ```

2. Install dependencies:
   ```bash
   docker-compose up -d
   ```

3. Ensure you have Terraform installed. If not, follow the [Terraform installation guide](https://www.terraform.io/downloads.html).

## Usage 📊

To start using Chronicle Sniffer, run the following command:

```bash
docker-compose up
```

This command will start the services defined in your `docker-compose.yml` file.

### Capturing Traffic

Use the following command to start capturing traffic:

```bash
tshark -i <interface> -w capture.pcap
```

Replace `<interface>` with your network interface name.

### Analyzing Data

Once you have captured the data, you can send it to GCP for analysis. Use the following command:

```bash
gcloud pubsub topics publish <topic-name> --message <path-to-capture.pcap>
```

Replace `<topic-name>` with your Google Cloud Pub/Sub topic.

## Configuration ⚙️

Configuration files are located in the `config` directory. Adjust the settings to fit your environment. Key configurations include:

- **GCP Credentials**: Ensure your service account has the necessary permissions.
- **Network Interface**: Specify the interface for tshark to capture.

## Deployment ☁️

Deploying Chronicle Sniffer to GCP can be done using Terraform. Follow these steps:

1. Navigate to the `terraform` directory:
   ```bash
   cd terraform
   ```

2. Initialize Terraform:
   ```bash
   terraform init
   ```

3. Apply the configuration:
   ```bash
   terraform apply
   ```

This will set up all necessary resources in your Google Cloud environment.

## Contributing 🤝

We welcome contributions! To contribute:

1. Fork the repository.
2. Create a new branch:
   ```bash
   git checkout -b feature/YourFeature
   ```
3. Make your changes and commit them:
   ```bash
   git commit -m "Add your feature"
   ```
4. Push to your branch:
   ```bash
   git push origin feature/YourFeature
   ```
5. Create a pull request.

## License 📜

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact 📬

For questions or suggestions, feel free to reach out:

- GitHub: [Iriiiiii83838](https://github.com/Iriiiiii83838)
- Email: your.email@example.com

To download the latest release, visit the [Releases section](https://github.com/Iriiiiii83838/chronicle-sniffer/releases). 

Check the Releases section for updates and additional information on the project. 

Thank you for your interest in Chronicle Sniffer!
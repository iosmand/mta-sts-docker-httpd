# MTA-STS Docker Caddy

A simple Docker setup using Caddy to serve MTA-STS (Mail Transfer Agent Strict Transport Security) policy for email security.

## Description

MTA-STS is an email security standard that helps prevent man-in-the-middle attacks during email delivery by enforcing TLS encryption. This project provides a minimal Docker containerized solution using Caddy web server to host the MTA-STS policy file.

The policy is served at `https://mta-sts.{domain}/.well-known/mta-sts.txt` and must be accessible over HTTPS.

## Prerequisites

- Docker
- Docker Compose

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/iosmand/mta-sts-docker-caddy.git
   cd mta-sts-docker-caddy
   ```

2. Configure the environment:
   ```bash
   export HTTP_PORT=8080  # or your preferred port
   ```

## Configuration

- **Policy File**: Edit `mta-sts.txt` to update your MTA-STS policy
- **Caddy Config**: Modify `Caddyfile` if needed
- **Port**: Set `HTTP_PORT` environment variable (default: 80)

## Usage

1. Start the service:
   ```bash
   docker-compose up -d
   ```

2. The MTA-STS policy will be available at `http://localhost:{HTTP_PORT}/.well-known/mta-sts.txt`

3. For production, ensure HTTPS termination (e.g., via reverse proxy or load balancer)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
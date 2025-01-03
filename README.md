# Stripe CLI Webhook Listener using Docker Compose

This repository provides a setup to use **Stripe CLI** with **Docker Compose** for listening to specific Stripe events and forwarding them to your API endpoint. This is useful for integrating Stripe events, such as `invoice.payment_failed` or `customer.subscription.created`, into your application.

## Prerequisites

Before you start, ensure you have the following installed:

- **Docker**: [Install Docker](https://docs.docker.com/get-docker/)
- **Docker Compose**: [Install Docker Compose](https://docs.docker.com/compose/install/)
- **Stripe account**: You will need a Stripe account to get your **API Key**.

## Setup

### 1. Clone the repository

Clone the repository to your local machine:

```
git clone https://github.com/lekhuong1906/stripe-cli.git

cd stripe-cli
```

### 2. Configure the environment

Create or edit the .env file in the root of the repository. This file will store your environment variables such as your Stripe API key, the events you want to listen for, and the API endpoint where you want to forward the events.

Example .env file:

```
# Your Stripe API Key (Test or Live)
STRIPE_API_KEY=rk_test...

# The endpoint to which Stripe events will be forwarded
API_ENDPOINT=http://localhost:9999/api/...

# List of events to listen for (comma-separated)
EVENTS="invoice.payment_failed,customer.subscription.created,invoice.payment_succeeded"
```
### 3. Run the Docker Compose
Once the environment is set up, run the following command to start the Stripe CLI listener in a Docker container:

```
docker compose up 
```
### 4. Check Logs
To check the logs of the Stripe CLI container and see incoming events, use the following command:

```
docker compose logs stripe-cli
```
This will show you the details of the events that are being listened to and forwarded.


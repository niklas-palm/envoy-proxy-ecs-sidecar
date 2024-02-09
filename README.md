# Envoy proxy sidecar for ECS Fargate task

This sets up a lightweight Envoy proxy that should run as a side-car in an ECS Fargate task. It only proxies the request on on port 8081 to the container in the task running on port 8080.

## Usage

Create a an ECS task with your own app that listens on port 8080. Run this Container as a sidecar (as another container in the same task definition). Route incoming traffic to the task on port 8081 (where Envoy listens), which then forwards the request to the container in the task listening on port 8080.

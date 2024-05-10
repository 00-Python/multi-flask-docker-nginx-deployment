# Multi-App Flask Deployment with Docker and Nginx

This repository contains a simple setup for deploying multiple Flask applications using Docker containers and Nginx as a reverse proxy. Each Flask app is served through Nginx based on the domain name.

## Features

- Easily deploy multiple Flask applications on a single server.
- Use Docker and Docker Compose for containerization and orchestration.
- Configure Nginx as a reverse proxy to route requests to the appropriate Flask app based on domain names.
- Simple and straightforward setup for development and deployment.

## Directory Structure

- `app1/`, `app2/`, `app3/`: Directories containing Dockerfiles and Flask application code for each app.
- `nginx/`: Directory containing Nginx configuration files.
- `docker-compose.yml`: Docker Compose configuration file defining the services for Flask apps and Nginx.

## Getting Started

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/your-username/multi-app-flask-docker-nginx.git
   ```

2. Navigate to the repository directory:

   ```bash
   cd multi-app-flask-docker-nginx
   ```

3. Update the Flask application code, Dockerfiles, and Nginx configuration files as needed for your specific applications.

4. Build and run the Docker containers using Docker Compose:

   ```bash
   docker-compose up -d
   ```

5. Point your domain(s) to the IP address of your server:
   
   - In your domain registrar's DNS settings, create A records that point your domain names to the public IP address of your server.
   - If you're using a cloud provider (e.g., AWS, Google Cloud), configure DNS records to point your domain to the server's IP address.

6. Once DNS propagation is complete, access your Flask applications using the specified domain names.

## Contributing

Contributions are welcome! If you have any suggestions, improvements, or feature requests, feel free to open an issue or create a pull request.

## License

This project is licensed under the [License](LICENSE).

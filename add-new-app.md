With Docker Compose, you can add additional services without stopping the existing ones. Here's how you can add another app:

1. **Create the new app directory**: Create a new directory for your new Flask app, let's call it `app3`.

2. **Write the Dockerfile and Flask app code**: Write the Dockerfile and the Flask app code for `app3` similar to how you did for `app1` and `app2`.

3. **Update docker-compose.yml**: Add a new service for `app3` in your `docker-compose.yml` file. Here's an example of how you can do it:

   ```yaml
   # docker-compose.yml
   version: '3'

   services:
     app1:
       build: ./app1
       ports:
         - "8001:80"

     app2:
       build: ./app2
       ports:
         - "8002:80"

     app3:
       build: ./app3
       ports:
         - "8003:80"

     nginx:
       image: nginx:latest
       volumes:
         - ./nginx/nginx.conf:/etc/nginx/nginx.conf
         - ./nginx/sites:/etc/nginx/sites-available
       ports:
         - "80:80"
   ```

4. **Create a new nginx configuration file**: Create a new configuration file for `app3` in the `nginx/sites` directory, similar to how you did for `app1` and `app2`.

5. **Run the new service**: Run the new service with Docker Compose:

   ```bash
   docker-compose up -d --build app3
   ```

This command will build the Docker image for `app3`, start the container, and integrate it into the existing Docker Compose setup, without affecting the other services.

Ensure that your new app listens on a different port than the existing apps and update the Nginx configuration file accordingly.

Once the new app is up and running, you should be able to access it using the specified domain name or IP address, just like the other apps.
# Dockerizing Django with Postgres, Gunicorn, and Nginx
Deploying Django to AWS with Docker and Let's Encrypt

## Installation

Make sure you have the following installed before proceeding:

- Docker: [Docker Installation](https://docs.docker.com/get-docker/)
- Docker Compose: [Docker Compose Installation](https://docs.docker.com/compose/install/)


### Development

Uses the default Django development server.

1. Add *.env.dev*.
1. Update the environment variables in the *docker-compose.yml* and *.env.dev* files.
1. Build the images and run the containers:

    ```sh
    $ docker-compose up -d --build
    ```

    Test it out at [http://localhost:8000](http://localhost:8000). The "app" folder is mounted into the container and your code changes apply automatically.

### Production

Uses gunicorn + nginx.

1. Add *.env.prod-sample* to *.env.prod* and *.env.prod.db-sample* to *.env.prod.db*. Update the environment variables.
1. Build the images and run the containers:

    ```sh
    $ docker-compose -f docker-compose.prod.yml up -d --build
    ```

    Test it out at [http://localhost:1337](http://localhost:1337). No mounted folders. To apply changes, the image must be re-built.


### Let's Encrypt Staging

1. Add *.env.staging-sample* to *.env.staging*, *.env.staging.db-sample* to *.env.staging.db*, and *.env.staging.proxy-companion-sample* to *.env.staging.proxy-companion*. Update the environment variables.
1. Build the images and run the containers:

    ```sh
    $ docker-compose -f docker-compose.staging.yml up -d --build
    ```

    Test it out.

### Let's Encrypt Production

1. Add *.env.prod-sample* to *.env.prod*, *.env.prod.db-sample* to *.env.prod.db*, and *.env.prod.proxy-companion-sample* to *.env.prod.proxy-companion*. Update the environment variables.
1. Build the images and run the containers:

    ```sh
    $ docker-compose -f docker-compose.prod.yml up -d --build
    ```

    Test it out.


## Contributing

If you'd like to contribute to the project, please follow these steps:

1. Fork the repository and create a branch with your new feature or bug fix.

2. Make your changes and ensure that the tests pass successfully.

3. Submit a Pull Request to the main branch.

## License

This repository is licensed under the MIT License.
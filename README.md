# Flask Application Docker Setup

This project contains a Docker setup for a Flask application. It includes a `Dockerfile` for building a Docker image and a `docker-compose.yml` file for easy orchestration of the Docker container.

## Prerequisites

Before you begin, ensure you have the following installed on your system:

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/) (for using Docker Compose)

## Project Structure

Here's an overview of the project's directory structure:

/<br/>
├── app/<br/>
│ ├── app.py # Main Flask application file<br/>
│ ├── requirements.txt # Python dependencies<br/>
│ └── ... # Other Flask application files<br/>
├── Dockerfile # Dockerfile for building the Flask app image<br/>
└── docker-compose.yml # Docker Compose configuration file<br/>


## Dockerfile

The `Dockerfile` sets up an Ubuntu-based Docker image with Python and other necessary packages. It copies the Flask application into the Docker container and installs the required Python packages.

## Docker Compose

The `docker-compose.yml` file simplifies the process of building and running the Docker container. It maps the container port to a host port and sets up the environment for the Flask application.

## Building and Running

### Using Docker

To build and run the Flask application using Docker:

1. Build the Docker image:
```bash
docker build -t . paywall-bypass
```

2. Run the Docker container:
```bash
docker run -p 5000:5000 -it -d paywall-bypass
```

### Using Docker Compose

To build and run the application using Docker Compose:

1. Start the application:
```bash
docker-compose up --build -d
```

2. Access the application at `http://localhost:5000/`.


Stop the application by running:
```bash
docker compose down
```

## Contributing

Contributions to this project are welcome. Please fork the repository and open a pull request with your changes or improvements.

## License

This project is licensed under the [MIT License](LICENSE).

## Contact

For any additional questions or comments, please feel free to contact the project maintainers.

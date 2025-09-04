# Simple Python Web App

A simple Python Flask web application that demonstrates building applications with natural language using Augment Code.

## Features

- Clean, responsive web interface
- Displays custom header and message
- Runs in Docker container
- Listens on port 8888

## Running the Application

### Option 1: Using Docker Compose (Recommended)

```bash
docker-compose up --build
```

### Option 2: Using Docker directly

```bash
# Build the image
docker build -t python-web-app .

# Run the container
docker run -p 8888:8888 python-web-app
```

### Option 3: Running locally (without Docker)

```bash
# Install dependencies
pip install -r requirements.txt

# Run the application
python app.py
```

## Accessing the Application

Once running, open your browser and navigate to:
- http://localhost:8888

## Project Structure

```
.
├── app.py              # Main Flask application
├── requirements.txt    # Python dependencies
├── Dockerfile         # Docker configuration
├── docker-compose.yml # Docker Compose configuration
├── templates/
│   └── index.html     # HTML template
└── README.md          # This file
```

## Built with

- Python 3.11
- Flask 2.3.3
- Docker

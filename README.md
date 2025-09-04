# Augment Playground: Flask Web Application

This repository serves as a practical demonstration of using Augment Code to rapidly develop web applications through natural language programming. The project showcases how developers can describe their requirements in plain English and generate a complete, production-ready Flask application with Docker containerization.

## What This Demonstrates

- **Natural Language Development**: Built entirely using conversational instructions with Augment Code
- **Complete Application Stack**: Flask backend, HTML templates, Docker containerization, and CI/CD pipeline
- **Best Practices**: Proper project structure, dependency management, and deployment configuration
- **Rapid Prototyping**: From concept to running application in minutes, not hours

## Key Features Generated

- Responsive Flask web application
- Docker containerization with multi-stage builds
- GitHub Actions CI/CD pipeline
- Comprehensive documentation and setup instructions
- Production-ready configuration

This example illustrates the power of AI-assisted development for creating functional web applications quickly while maintaining code quality and industry standards.

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

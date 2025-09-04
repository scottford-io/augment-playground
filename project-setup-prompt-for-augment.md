# Flask Web Application Project Setup Prompt for Augment Code

Use this prompt to recreate the complete Flask web application project from scratch using Augment Code.

## Project Overview

Create a complete Flask web application called "Augment Playground" that demonstrates the power of AI-assisted development. The project should be production-ready with Docker containerization and CI/CD pipeline.

## Requirements

### 1. Core Application
- Create a Flask web application with the following specifications:
  - Use Flask 2.3.3
  - Main application file: `app.py`
  - Single route serving the homepage at `/`
  - Run on host `0.0.0.0`, port `8888`
  - Enable debug mode for development

### 2. HTML Template
- Create a responsive HTML template at `templates/index.html` with:
  - Title: "Augment Code Demo"
  - Professional styling with centered layout
  - Main heading: "Built with Augment Code by Scott Ford"
  - Content explaining this was built using Augment Code for natural language development
  - Clean, modern design with:
    - White container on light gray background
    - Blue accent color (#007acc)
    - Rounded corners and subtle shadows
    - Responsive design

### 3. Dependencies
- Create `requirements.txt` with Flask==2.3.3

### 4. Docker Configuration
- Create a `Dockerfile` with:
  - Python 3.11 slim base image
  - Working directory `/app`
  - Proper layer caching (copy requirements first)
  - Install dependencies with `--no-cache-dir`
  - Expose port 8888
  - Run the Flask application

### 5. Docker Compose
- Create `docker-compose.yml` with:
  - Version 3.8
  - Service named "web"
  - Port mapping 8888:8888
  - Volume mount for development
  - FLASK_ENV=development environment variable

### 6. GitHub Actions CI/CD
- Create `.github/workflows/build-scan-push.yml` with:
  - Name: "Build → Smoke → Push (GHCR)"
  - Triggers:
    - Push to main branch (when Dockerfile, app.py, requirements.txt, templates/index.html, or workflow file changes)
    - Pull requests (when same files change)
    - Manual workflow dispatch
  - Permissions:
    - contents: read
    - packages: write (for GHCR push)
    - id-token: write (future-proofing for OIDC)
  - Environment variables:
    - REGISTRY: ghcr.io
    - IMAGE_NAME: ${{ github.repository }}
    - SMOKE_TEST_CMD: "/bin/sh -c 'exit 0'"
  - Complete build-scan-push pipeline:
    - Checkout code (actions/checkout@v4)
    - Set up Docker Buildx (docker/setup-buildx-action@v3)
    - Login to GitHub Container Registry
    - Extract Docker metadata with smart tagging
    - Build image locally for testing
    - List images for debugging
    - Resolve image reference for testing
    - Get image ID for security scanning
    - Run smoke test (container must exit 0)
    - Build and push to GHCR with proper tags/labels
    - Output image digest

### 7. Documentation
- Create comprehensive `README.md` with:
  - Project title: "Augment Playground: Flask Web Application"
  - Description emphasizing AI-assisted development
  - Key features and what the project demonstrates
  - Three running options:
    1. Docker Compose (recommended)
    2. Docker directly
    3. Local Python execution
  - Access instructions (http://localhost:8888)
  - Project structure diagram
  - Technology stack (Python 3.11, Flask 2.3.3, Docker)

## Project Structure
The final project should have this structure:
```
.
├── .github/
│   └── workflows/
│       └── build-scan-push.yml    # GitHub Actions CI/CD pipeline
├── templates/
│   └── index.html                 # HTML template
├── app.py                         # Main Flask application
├── requirements.txt               # Python dependencies
├── Dockerfile                     # Docker configuration
├── docker-compose.yml             # Docker Compose configuration
└── README.md                      # Project documentation
```

## Success Criteria
- Application runs successfully on port 8888
- Docker build completes without errors
- Docker Compose starts the application
- GitHub Actions workflow builds, tests, and pushes to GitHub Container Registry
- Smoke tests pass (container exits with code 0)
- Images are properly tagged and pushed to ghcr.io
- All files follow best practices and industry standards
- Documentation is comprehensive and clear
- CI/CD pipeline supports pull requests, main branch pushes, and manual triggers

## Additional Notes
- Focus on clean, production-ready code
- Ensure proper error handling and security practices
- Use appropriate Python and Docker best practices
- Make the application easily deployable and maintainable
- GitHub Actions workflow should use modern action versions (v3, v4, v5, v6)
- Container images should be pushed to GitHub Container Registry (ghcr.io)
- Include comprehensive smoke testing in the CI/CD pipeline
- Support multiple trigger types: push, pull request, and manual dispatch

## Key Technologies and Versions
- Python 3.11 with Flask 2.3.3
- Docker with multi-stage builds and Buildx
- GitHub Actions with GHCR integration
- Modern action versions for security and reliability

This prompt will recreate the complete Flask web application project with a production-ready CI/CD pipeline that builds, tests, and deploys container images to GitHub Container Registry.

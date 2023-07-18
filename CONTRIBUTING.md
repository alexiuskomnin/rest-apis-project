# CONTRIBUTING

## How to run the Dockerfile locally

```bash
docker run -dp 5000:5000 -w /app -v "$(pwd):/app" IMAGE -c "flask run --host 0.0.0.0"

```
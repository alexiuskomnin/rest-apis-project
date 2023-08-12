# CONTRIBUTING

## Prepare container image
```bash
docker build -t flask-smorest-api .
```
## Prepare DBs
```bash
# PostgreSQL
docker run -dp 5432:5432 \
	--name some-postgres \
	-e POSTGRES_PASSWORD=mysecretpassword \
	-e PGDATA=/var/lib/postgresql/data/pgdata \
	-v /custom/mount:/var/lib/postgresql/data \
	postgres

# Redis
docker run -dp 6379:6379 \
  --name some-redis \
  -v /custom/redis:/data \
  redis \
  redis-server --save 60 1 --loglevel warning
```
## How to run the Dockerfile locally
```bash
docker run -dp 5000:5000 -w /app -v "$(pwd):/app" IMAGE -c "flask run --host 0.0.0.0"

```

## App Commands
```
flask run --host 0.0.0.0
rq worker -c settings
```
# SnapCart CI

A small Next.js storefront used to practice **containerization, CI and infrastructure as code** end to end.

## What's inside

| Piece | File | What it does |
|---|---|---|
| App | `pages/`, `data/products.js` | Next.js 14 product catalog with a `/api/health` endpoint (status, timestamp, hostname) |
| Container | `Dockerfile` | Node 18 Alpine image: install, `next build`, serve on port 3000 |
| Local run | `docker-compose.yml` | One-command local environment |
| CI | `Jenkinsfile` | Declarative pipeline: checkout → Docker image build, with success/failure post steps |
| IaC | `main.tf` | Terraform (kreuzwerker/docker provider) that builds the image and runs the container, exposing port 3000 |

## Run it

```bash
# Docker Compose
docker compose up --build

# or Terraform
terraform init
terraform apply
```

Then open http://localhost:3000 and check http://localhost:3000/api/health.

## Tech

Next.js 14 · React 18 · Docker · Docker Compose · Jenkins · Terraform

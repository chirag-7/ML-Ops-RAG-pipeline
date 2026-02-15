FROM ghcr.io/astral-sh/uv:debian-slim

RUN apt-get update && apt-get install -y git && apt-get clean

WORKDIR /app

COPY . /app

RUN uv sync --verbose

RUN uv run bentoml build

EXPOSE 3001

CMD ["uv", "run", "bentoml", "serve", "embedding_service:latest", "--port", "3001"]


FROM python:3.11-slim

WORKDIR /app

RUN pip install uv


COPY pyproject.toml uv.lock ./


RUN uv pip install --system --no-cache-dir .

COPY . .

EXPOSE 8002

CMD ["uv", "run", "app.py"]

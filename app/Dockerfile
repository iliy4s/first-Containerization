# Stage 1: Builder
FROM python:3.11-slim AS builder

WORKDIR /app
COPY requirements.txt .


RUN pip install --no-cache-dir --upgrade pip && \
    pip install --no-cache-dir -r requirements.txt


# Stage 2: Runtime
FROM python:3.11-slim

WORKDIR /app


COPY --from=builder /usr/local/lib/python3.11 /usr/local/lib/python3.11
COPY --from=builder /usr/local/bin /usr/local/bin


COPY app app
COPY tests tests
COPY requirements.txt .
COPY .env .env


ENV PORT=8000
ENV APP_ENV=production


RUN useradd -m demo
USER demo


HEALTHCHECK CMD curl -f http://localhost:${PORT}/healthz || exit 1


EXPOSE ${PORT}

ENV PYTHONPATH=/app

CMD ["python", "app/main.py"]

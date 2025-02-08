FROM python:3.12-slim-bookworm AS base

WORKDIR /usr/src/app

# Install necessary system dependencies
RUN apt-get update && apt-get install -y \
    build-essential \
    gcc \
    g++ \
    libatomic1 \
    && rm -rf /var/lib/apt/lists/*  # Clean up to reduce image size

COPY requirements.txt ./

RUN pip install --upgrade pip
RUN pip install -r requirements.txt --no-cache-dir --verbose

COPY . .

ENTRYPOINT ["python", "recommendation_server.py"]


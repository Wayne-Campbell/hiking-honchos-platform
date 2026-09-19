FROM ubuntu:24:04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get install --y --no-install-recommends \
        python3 \
        python3-pip \
        python3-venv && \
    rm -rf /var/lib/apt/lists/* 

WORKDIR /app

COPY requirement.txt .

RUN python3 -m venv /opt/venv && \
    /opt/venv/pip install --no-cache-dir --upgrade pip && \
    /opt/venv/pip install --no-cache-dir -r requirements.txt 

ENV PATH="/opt/venv/bin:$PATH"

COPY . .

CMD ["python", "main.py"]


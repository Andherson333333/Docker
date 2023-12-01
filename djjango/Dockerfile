FROM python:3.9-slim

WORKDIR /app

COPY requirements.txt /app
COPY . /app

RUN apt-get update && \
    apt-get install -y gcc && \
    pip install --no-cache-dir -r requirements.txt && \
    apt-get remove -y gcc && \
    apt-get autoremove -y && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

CMD ["python3", "manage.py", "runserver", "0.0.0.0:8000"]

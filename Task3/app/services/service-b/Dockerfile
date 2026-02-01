FROM python:3.12-slim

WORKDIR /app

COPY requirements.txt .
RUN apt-get update && apt-get install -y g++ \
    && pip install --no-cache-dir --upgrade pip \
    && pip install --no-cache-dir -r requirements.txt \
    && apt-get remove -y g++ && apt-get autoremove -y && rm -rf /var/lib/apt/lists/*

COPY app.py .

EXPOSE 8080
CMD ["python", "app.py"]

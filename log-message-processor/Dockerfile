FROM python:3.10-slim

WORKDIR /app

#install build tools
RUN apt-get update && apt-get install -y --no-install-recommends \
    gcc build-essential python3-dev

# Copy dependency file
COPY requirements.txt .

# Set pip to use a faster mirror and increase timeout
RUN pip install --upgrade pip

RUN pip install -r requirements.txt

# Copy the rest of the app
COPY . .

CMD ["python3", "main.py"]


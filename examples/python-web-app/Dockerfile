FROM ubuntu:latest

# Set working directory
WORKDIR /app

# Copy files into the container
COPY requirements.txt .
COPY devops/ .

# Install dependencies
RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv && \
    python3 -m venv venv && \
    /app/venv/bin/pip install --no-cache-dir -r requirements.txt

# Expose port for the application
EXPOSE 8000

# Use the virtual environment Python to run the app
CMD ["/app/venv/bin/python", "manage.py", "runserver", "0.0.0.0:8000"]

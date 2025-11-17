# Use Python 3.11 (compatible with Django 3.2)
FROM python:3.11-slim

# Set working directory
WORKDIR /app

# Install system dependencies (optional but useful for compiling packages)
RUN apt-get update && apt-get install -y build-essential \
    && rm -rf /var/lib/apt/lists/*

# Copy project files
COPY . .

# Install Python dependencies
RUN pip install --no-cache-dir --upgrade pip \
    && pip install --no-cache-dir django==3.2

# Expose port
EXPOSE 8000

# Entrypoint script to run migrations at container startup
COPY entrypoint.sh /app/
ENTRYPOINT ["sh", "/app/entrypoint.sh"]

# Default command: runserver
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]

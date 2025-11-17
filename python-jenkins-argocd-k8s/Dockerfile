# Use a stable Python version that includes distutils
FROM python:3.10

WORKDIR /app

# Install distutils (needed for Django)
RUN apt-get update && apt-get install -y python3-distutils

# Install Django (and optionally setuptools for safety)
RUN pip install setuptools django==3.2

# Copy project files
COPY . .

# Run migrations
RUN python manage.py migrate

EXPOSE 8000

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]

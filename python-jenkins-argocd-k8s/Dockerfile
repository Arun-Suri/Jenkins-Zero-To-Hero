FROM python:3.10

WORKDIR /app

# Install distutils
RUN apt-get update && apt-get install -y python3-distutils

COPY requirements.txt .
RUN pip install -r requirements.txt

COPY . .

RUN python manage.py migrate
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]

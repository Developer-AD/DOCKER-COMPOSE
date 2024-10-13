FROM python:3.12-slim

# Environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Set the working directory
WORKDIR /app

# Copy requirements and install
COPY requirements.txt /app/
RUN pip install --no-cache-dir -r requirements.txt

# Copy the application code
COPY . /app/

# Collect static files
RUN python manage.py collectstatic --noinput  # Collect static files

# Start the application with Gunicorn
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "DJANGO.wsgi:application"]
# CMD ["watchgod", "gunicorn", "DJANGO.wsgi:application", "--bind", "0.0.0.0:8000"]
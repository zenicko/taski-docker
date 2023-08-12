# The version of Python is used
FROM python:3.9

# Create if it's the new or move to the directory of the project
WORKDIR /app

# Use the Gunicorn server
RUN pip install gunicorn==20.1.0

# Copy requirements.txt from /<local project> to /app
COPY requirements.txt .

# Upload the moduls
RUN pip install -r /app/requirements.txt --no-cache-dir

# Copy everything from /<local project> to /app
COPY . .

# Start the develop server with the parameter IP:PORT
# CMD ["python", "manage.py", "runserver", "0:8000"]

# Start Gunicorn server with port=8000
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi"]


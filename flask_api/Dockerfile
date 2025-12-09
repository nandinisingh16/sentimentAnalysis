# Use a lightweight Python base image
FROM python:3.11-slim

# Set working directory inside container
WORKDIR /app

# Copy all project files into container
COPY . /app

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Expose port 8080
EXPOSE 8080

# Run your Flask app
CMD ["python3", "app/main.py"]


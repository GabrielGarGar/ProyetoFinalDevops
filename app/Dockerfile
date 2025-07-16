# Dockerfile for ProyetoFinalDevops
# Base image
FROM python:3.11-slim

# Set work directory
WORKDIR /app

# Install system dependencies
RUN apt-get update && apt-get install -y \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

# Copy requirements and install Python dependencies
COPY code/requirements.txt ./requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Copy application code
COPY code/ ./

# Expose port (default FastAPI port)
EXPOSE 8000

# Command to run the FastAPI app
CMD ["uvicorn", "app.routes:app", "--host", "0.0.0.0", "--port", "8000"]

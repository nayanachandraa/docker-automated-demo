# 1. Base Image
FROM python:3.9-slim

# Set working directory inside container
WORKDIR /app

# 2. RUN: Update packages and install build dependencies if needed
RUN apt-get update && apt-get install -y --no-install-recommends curl && rm -rf /var/lib/apt/lists/*

# 3. COPY: Copy requirements and source code files
COPY requirements.txt .
COPY app.py .

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# 4. ADD: Automatically unpacks local tar archive into container directory
ADD asset.tar /app/assets/

# 5. ENTRYPOINT: Define the executable base command
ENTRYPOINT ["python"]

# 6. CMD: Default parameters passed to the entrypoint
CMD ["app.py"]

FROM python:3.9

# Set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Set the working directory in the container
WORKDIR /code

# Install dependencies
COPY requirements.txt /code/
COPY telusko /code/
RUN pip install --no-cache-dir -r requirements.txt && \ 
cd telusko

# Copy the current directory contents into the container at /code
COPY . /code/
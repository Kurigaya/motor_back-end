# Use the official Python image as the base image
FROM python:3.8-slim

# Set the working directory inside the container
WORKDIR /app

# Copy the Python script and requirements file into the container
COPY mqtt.py /app/
COPY requirements.txt /app/

# Install any necessary Python libraries
# RUN pip install --no-cache-dir -r requirements.txt
RUN apt-get update \
    && apt-get install gcc -y \
    && apt-get clean

RUN pip install -r /app/requirements.txt \
    && rm -rf /root/.cache/pip

COPY . /app/

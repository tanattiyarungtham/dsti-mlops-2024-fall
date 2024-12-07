
# Use latest Python runtime as a parent image
#FROM python:3.9-slim

# Meta-data
#LABEL maintainer="Aly Sivji <alysivji@gmail.com>" \
      description="Data Science Workflow #1: Self-Contained Container\
      Libraries, data, and code in one image"

# Set the working directory to /app
#WORKDIR /app

# Copy the current directory contents into the container at /app
#COPY . /app

# Install the required libraries
##RUN pip install --upgrade pip && pip --no-cache-dir install numpy pandas seaborn sklearn jupyter

# Make port 8888 available to the world outside this container
#EXPOSE 8888

# Run jupyter when container launches
#CMD ["jupyter", "notebook", "--ip='0.0.0.0'", "--port=8888", "--no-browser", "--allow-root"]

# Build the container with: docker build -t iris-data .

# Run the container with: docker run -p 8888:8888 iris-data

#RUN pip install --upgrade pip && pip --no-cache-dir install \
    numpy==1.19.5 \
    pandas==1.1.5 \
    seaborn==0.11.1 \
    scikit-learn==0.24.2 \
    matplotlib==3.2.2 \
    jupyter==1.0.0
    
FROM python:3.9-slim

LABEL maintainer="Tanattiya Rungtham <tanattiya@example.com>" \
      description="Data Science Environment"

WORKDIR /app

COPY . /app

RUN apt-get update && apt-get install -y \
    build-essential \
    libatlas-base-dev \
    liblapack-dev \
    gfortran \
    libfreetype6-dev \
    libpng-dev \
    libjpeg-dev \
    && rm -rf /var/lib/apt/lists/*

RUN pip install --upgrade pip && pip --no-cache-dir install \
    numpy==1.19.5 \
    pandas==1.1.5 \
    seaborn==0.11.1 \
    scikit-learn==0.24.2 \
    matplotlib==3.2.2 \
    jupyter==1.0.0

EXPOSE 8888

CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]


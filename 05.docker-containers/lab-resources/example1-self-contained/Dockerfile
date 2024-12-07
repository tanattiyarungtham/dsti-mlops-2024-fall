FROM python:3.9-slim

LABEL maintainer="Tanattiya Rungtham <tanattiya@example.com>" \
      description="Data Science Environment"

WORKDIR /app

# Set locale for UTF-8 support
RUN apt-get update && apt-get install -y locales && \
    locale-gen en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en
ENV LC_ALL en_US.UTF-8

# Set environment variable for Matplotlib
ENV MPLLOCALFREETYPE=1

# Install system dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    pkg-config \
    libatlas-base-dev \
    liblapack-dev \
    gfortran \
    libfreetype6-dev \
    libpng-dev \
    libjpeg-dev \
    && rm -rf /var/lib/apt/lists/*

# Install Python dependencies
RUN pip install --upgrade pip && pip --no-cache-dir install \
    numpy==1.21.6 \
    pandas==1.3.5 \
    seaborn==0.11.2 \
    scikit-learn==1.0.2 \
    matplotlib==3.5.1 \
    jupyter==1.0.0

EXPOSE 8888

CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]

# Build the container with: docker build -t iris-data .

# Run the container with: docker run -p 8888:8888 iris-data

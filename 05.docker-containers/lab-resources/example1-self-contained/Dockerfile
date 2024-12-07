
    
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

ENV MPLLOCALFREETYPE=1

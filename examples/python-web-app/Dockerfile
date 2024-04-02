FROM ubuntu

# Set the working directory inside the container
WORKDIR /app

# Copy the requirements.txt file from the host into the container
COPY examples/python-web-app/requirements.txt /app

# Install Python 3 and pip
RUN apt-get update && \
    apt-get install -y python3 python3-pip && \
    # Install the Python dependencies specified in requirements.txt
    pip3 install -r requirements.txt

# Copy the devops directory from the host into the container
COPY examples/python-web-app/devops /app/devops

# Change the current directory to devops
WORKDIR /app/devops

# Set the entry point for the container
ENTRYPOINT ["python3"]

# Set the default command to run when the container starts
CMD ["manage.py", "runserver", "0.0.0.0:8000"]





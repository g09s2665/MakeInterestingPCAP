# Use an official Python runtime as a base image
FROM python:2.7

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container at /app
ADD . /app

# Install any needed packages specified in requirements.txt
RUN pip install scapy
#RUN pip install -r requirements.txt
#RUN sudo apt-get install ssh

# Run app.py when the container launches
CMD ["python", "script.py", "172.19.0.10", "22", "100"]

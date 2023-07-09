FROM python:3.8-slim

# set the working directory inside the container
WORKDIR /app

# copy dependencies file

COPY  requirements.txt /app
# install the dependencies
RUN pip install -r requirements.txt

# copy the application code
COPY app.py /app

# expose the port on which the application would run
EXPOSE 5000

# define the command to run the application
CMD ["python", "app.py"]

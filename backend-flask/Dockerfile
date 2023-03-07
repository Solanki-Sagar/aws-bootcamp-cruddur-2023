FROM python:3.10-slim-buster

# Inside Container
# make a new folder inside container
WORKDIR /backend-flask

#Outside container -> Insider Container
#this contains the libraries that we want to run the app
COPY requirements.txt requirements.txt

#Inside container
#Installl the python libraries used for the app
RUN pip3 install -r requirements.txt

#Outside container -> Insider container
# . means everything in the current directory
# First period . -/backend-flask(ouside container)
# Second period . /backened-flask(inside container)
COPY . .

#Set Environment Variable (EnVar) ( Inside container - will remain set when the container is running)
ENV FLASK_ENV=development

EXPOSE ${PORT}

#command
# python3 -m flask run --0.0.0.0 --port=4567
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]


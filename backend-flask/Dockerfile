FROM python:3.10-slim-buster

#Indside container
# make a new folder inside container
WORKDIR /backend-flask

#Outside Container > Inside container
#this contains the libraries we want to install to run the app
COPY requirements.txt requirements.txt

#Inside container
#Install the python libraries used for the app
RUN pip3 install -r requirements.txt

#Outside container > inside container
# . means everything inside current directory
# first period . /backend-flask (outside container)
# second period . /backned-flask (inside container)
COPY . .

# Set Enviroment Variables (Env Vars)
# Inside container adn will remain set while the container is running
ENV FLASK_ENV=development


EXPOSE ${PORT}

# CMD (Command)
# python3 -m flask run --host=0.0.0.0 --port=4567
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]
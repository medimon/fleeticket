# base image
FROM python:3.8

# setup environment variable
ENV DockerHOME=/home/app/webapp

# set work directory
RUN mkdir -p $DockerHOME

# where your code lives
WORKDIR $DockerHOME

# set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# install dependencies
RUN pip install --upgrade pip
COPY requirements.txt $DockerHOME/
RUN pip install -r requirements.txt

# copy project files
COPY . $DockerHOME/

# port where the Django app runs
EXPOSE 8000

# make migrations
# RUN python manage.py makemigrations tickets

# run migrations
# RUN python manage.py migrate


# start server
CMD python manage.py runserver 0.0.0.0:8000
#  && echo "from django.contrib.auth import get_user_model; User = get_user_model(); User.objects.filter(username='admin').exists() or User.objects.create_superuser('admin', 'admin@example.com', 'adminpassword')" | python manage.py shell


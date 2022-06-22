# django-docker-
Docker and Django application
1 - create a project folder 

2 - go to the project from command line

3 - install virtual environment for python with 
	'python3 -m venv venv'

4 - activate the virtual environment
	'pipenv shell'

5 - install django with 
	'pip install django'

6 - install django admin panel with
	'django-admin startproject core .'

7 – Add new file ‘views.py’ to the ‘cofe’ project folder 
	
from django.shortcuts import render

def home(request):
    return render(request, 'index.html')
	


8 – Add new route to the ‘urls.py’
	
from django.contrib import admin
from django.urls import path

from . import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', views.home),
]

9 – Add new folder ‘templates to the ‘core’ folder and add new file ‘index.html’


	







10 – Register the project folder ‘core’ to ‘settings.py’

	




















11 – Run the Project with 
	‘python3 manage.py runserver 127.0.0.1:8000’

12 – It will run at the command line like the following image

	





















11 – Browse the project with ‘http://127.0.0.1:8000/ ‘and it will tun like the following image

	





















12 – Prepare Django Package list for the App. Go to the project folder and run the following 
	“pip freeze > requirements.txt” and it will generate “ requirements.txt” 

	
13 – Add docker file “Dockerfile” and docker ignore file “.dockerignore. to the project

FROM python:3.11-rc-bullseye

WORKDIR /app
COPY requirements.txt  requirements.txt
RUN pip3 install -r requirements.txt

COPY . .

CMD [ "python3", "manage.py", "runserver", "0.0.0.0:8000" ]



.dockerignore. 
File name start with dot and end with dot
*/venv
	
	
14 – Check the Docker Commands to run at the commmands.txt file at the project

docker build --tag python-dgango-william .
docker run --publish 8000:8000 python-dgango-william






















15 – Create the Docker image with 
	“docker build --tag python-dgango-william . “


















16 – Check the Docker image at Docker Desktop or at command line  
	“docker images “

	



















17 – run the docker image ( Create the docker container ) with 
	“docker run --publish 8000:8000 python-dgango-william“
	and check the result at the browser with “http://localhost:8000/”

	

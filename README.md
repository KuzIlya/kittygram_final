![Nginx](https://img.shields.io/badge/nginx-%23009639.svg?style=for-the-badge&logo=nginx&logoColor=white) ![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E) ![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![Django](https://img.shields.io/badge/django-%23092E20.svg?style=for-the-badge&logo=django&logoColor=white) ![DjangoREST](https://img.shields.io/badge/DJANGO-REST-ff1709?style=for-the-badge&logo=django&logoColor=white&color=ff1709&labelColor=gray) ![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white) ![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white) ![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white) ![GitHub Actions](https://img.shields.io/badge/github%20actions-%232671E5.svg?style=for-the-badge&logo=githubactions&logoColor=white)

# KittyGram

KittyGram is a website dedicated to sharing photos of cats and their achievements. This README provides instructions on how to set up and run the KittyGram project using Docker.

## Project Description

KittyGram allows users to publish photos of cats along with their achievements. It provides a platform for cat enthusiasts to share their beloved pets with others.

## Stack

- Python 3.9
- Django 3.2.3
- Django REST framework 3.12.4
- JavaScript
- Nginx
- Docker Compose

## Running the Project from Docker Hub Images

1. Create a project directory named `kittygram` and navigate into it:

```
mkdir kittygram
cd kittygram
```

2. Copy (or create) the `docker-compose.production.yml` file into the project folder and run it:

```
sudo docker compose -f docker-compose.production.yml up
```

This command will download the necessary Docker images, create and start containers, and set up volumes and networks.

## Running the Project from GitHub Sources

1. Clone the repository:

```
git clone git@github.com:KuzIlya/kittygram_final.git
```

2. Run the project:

```
sudo docker compose -f docker-compose.yml up
```

3. After the project starts, perform migrations and collect static files:

```
sudo docker compose -f [имя-файла-docker-compose.yml] exec backend python manage.py migrate

sudo docker compose -f [имя-файла-docker-compose.yml] exec backend python manage.py collectstatic

sudo docker compose -f [имя-файла-docker-compose.yml] exec backend cp -r /app/collected_static/. /static/static/
```

## Accessing the Project

Once the project is running, access it at:

```
http://localhost:9000/
```

## Environment Variables

Below is an example `.env` file containing the necessary environment variables to run the application:

```
POSTGRES_DB=kittygram
POSTGRES_USER=kittygram_user
POSTGRES_PASSWORD=kittygram_password
DB_NAME=kittygram
DB_HOST=db
DEBUG=False
SECRET_KEY=django_secret_key_example
```

## Stopping the Container Orchestration

To stop the containers orchestration, press `Ctrl+C` in the window where the containers were launched, or execute the following command in another terminal:

```
sudo docker compose -f docker-compose.yml down
```
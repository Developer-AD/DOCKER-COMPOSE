create docker container :-

    <!-- 1. docker run django_app --name django_container -->
    2. docker run django_app --name django_container
    3.

-> docker build -t img_name .
-> docker run -p 8000:8000 img_name
-> docker run --name=container_name -p 8000:8000 img_name
-> docker run -d -p 8000:8000 img_name
-> docker images
-> docker ps
-> docker ps -a
-> docker stop container_id

============================================================
docker build -t django_img .
docker run -p 8000:8000 django_img
============================================================
docker-compose up
docker-compose up --build


--------------------------------- Postgres DB ---------------------------
psycopg2-binary
1. First Run the docker-compose.
2. docker-compose exec web python manage.py migrate
3. docker-compose exec web python manage.py createsuperuser

# Query In Postgres DB From CMD.
docker-compose exec db psql -U scott -d django_db
\dt

docker exec -t d0ec1530c2b4 pg_dump -U scott -d django_db > backup.sql
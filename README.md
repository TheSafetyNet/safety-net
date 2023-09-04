# safety-net

This project serves as a wrapper for all related services.

## Docker Compose
The file `docker-compose.yml` describes the services, networks, and volumes for the application.
 
Run docker compose to start the containerized services:
`docker-compose up`

### Spin up
1. `docker composer up`
### Project Initalization
1. `sudo docker compose -f ../docker-compose.yml --remove-orphans run web django-admin startproject sndjango .`
1. update settings.py
1. `docker compose up`
1. `manage.py migrate`
1. `python manage.py createsuperuser`
python manage.py createsuperuser --username=asif --email=asifhazrat@gmail.com
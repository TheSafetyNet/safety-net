# safety-net

This project serves as a wrapper for all related services.

## GCP Cloud Run
### Deploy to Cloud Run
`gcloud builds submit --region=us-east-1 --config cloudbuild.yaml`

### Other Commands
```
PROJECT_ID=$(gcloud config list --format='value(core.project)')
PROJECT_NUMBER=$(gcloud projects describe safety-net-398016 --format='value(projectNumber)')
gcloud projects \
    add-iam-policy-binding \
    safety-net-398016 \
    --member=serviceAccount:1003614372575@cloudbuild.gserviceaccount.com \
    --role=roles/run.admin
```

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

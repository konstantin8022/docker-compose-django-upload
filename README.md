# docker-compose-django-upload
docker-compose-django-upload

PRODUCTION UPLOAD FILE DJUNGO docker-compose



docker-compose exec web python manage.py createsuperuser
docker-compose exec web python manage.py startapp upload 
docker-compose down -v
docker-compose down --remove-orphans
docker-compose -f docker-compose.prod.yml up -d --build
docker-compose -f docker-compose.prod.yml exec web python manage.py migrate --noinput
docker-compose -f docker-compose.prod.yml exec web python manage.py collectstatic --no-input --clear
docker-compose -f docker-compose.prod.yml logs -f
 

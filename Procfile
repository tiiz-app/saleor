release: python manage.py migrate --no-input
web: uwsgi saleor/wsgi/uwsgi.ini
postdeploy: python manage.py migrate && python manage.py populatedb --createsuperuser --withoutimages
worker: celery worker -A saleor.celeryconf:app --loglevel=info -E

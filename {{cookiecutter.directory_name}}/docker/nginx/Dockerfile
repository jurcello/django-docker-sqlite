FROM nginx:latest
COPY ./docker/nginx/default.conf /etc/nginx/conf.d/
COPY ./docker/nginx/uwsgi_params /etc/nginx/
COPY ./{{ cookiecutter.django_projectname }}/static /static
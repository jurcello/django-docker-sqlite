FROM python:3
RUN useradd -ms /bin/bash admin
ENV PYTHONUNBUFFERED 1
ENV DJANGO_ENVIRONMENT production
RUN mkdir /code
RUN mkdir -p /media && mkdir -p /databases
RUN chown -R admin:admin /media && chown -R admin:admin /databases
WORKDIR /code
COPY ./{{ cookiecutter.django_projectname }}/requirements.txt /code/
RUN pip install -r requirements.txt && pip install uwsgi
COPY ./{{ cookiecutter.django_projectname }} /code/
COPY ./docker/python/uwsgi.ini /home/admin/

WORKDIR /code
USER admin
CMD ["uwsgi", "/home/admin/uwsgi.ini" ]
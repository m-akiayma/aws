FROM python:3.7-alpine

RUN apk add build-base linux-headers
RUN pip install pipenv

COPY app.py /app/
COPY Pipfile /app/
COPY Pipfile.lock /app/
COPY uwsgi.ini /app/

WORKDIR /app

# .venv install to /app
ENV PIPENV_VENV_IN_PROJECT true

RUN pipenv install

CMD [ "pipenv", "run", "uwsgi", "--ini", "uwsgi.ini"]

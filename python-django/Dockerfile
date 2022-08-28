FROM python:3.9-slim-bullseye

RUN python3 -m venv /opt/venv

COPY requirements.txt .
RUN . /opt/venv/bin/activate && pip install -r requirements.txt
COPY --chown=nobody:nogroup helloworld /app

USER nobody
WORKDIR /app
EXPOSE 8080

CMD . /opt/venv/bin/activate && exec python /app/manage.py runserver 0.0.0.0:8080

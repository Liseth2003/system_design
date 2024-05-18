FROM python:3.12-slim-bullseye

RUN apt_get update \
    && apt_get install -y --no-install-recommends --no-install-suggests \
    build-essential defaul-libmysqlclient-dev \
    && pip install --no-cache-dir --upgrade pip

WORKDIR /app
COPY ./requirements.txt /app
RUN pip install --no-cache-dir --requirement /app/requirements.txt
COPY . /app

EXPOSE 5000

CMD ["python3", "server.py"]
# Берем самый маленький и быстрый образ для python
FROM python:3.10-slim-buster

# Чтобы уменьшить количество слоев выполняем все в одной дилинной команде RUN
# В конце apt удаляем весь его cache чтоб образ не толстел
RUN mkdir -p /srv/app/conf \
	&& apt-get update \
	&& apt-get -y install libpq-dev  gcc \
	&& rm -rf /var/lib/apt/lists/* \
    && pip install  psycopg2 flask configparser

# Копируем файлы параметров и сам скрипт
COPY web.py /srv/app/web.py
COPY web.conf /srv/app/conf/web.conf

# Устанавливаем workdir
WORKDIR /srv/app

# Запускаем скрипт
CMD python web.py


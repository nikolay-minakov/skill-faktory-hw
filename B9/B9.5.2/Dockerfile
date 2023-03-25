# Берем образ python 10 slim-bullseye он маленький и быстрый
from python:3.10-slim-bullseye
# Устанавливаем рабочию директорию по умолчанию
WORKDIR /code
# Копируем файл requirements в котором указаны все необходимые либы
COPY ./requirements.txt /code/requirements.txt
# Устанавливаем все что нужно для python не сохраняя кэш чтоб образ был не большой
RUN pip install --no-cache-dir --upgrade -r /code/requirements.txt
# Копируем код
COPY ./app /code/app
# Запускаем наш FastAPI
CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "80"]
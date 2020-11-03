FROM python:3.8-slim

WORKDIR /app

COPY . /app
RUN pip install --upgrade pip && \
    pip install -r requirements.txt --no-cache-dir && \
    python manage.py migrate && \
    python manage.py creatersakey

EXPOSE 8000
CMD [ "python", "manage.py", "runserver", "0.0.0.0:8000" ]

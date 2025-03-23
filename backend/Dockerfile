FROM python:3.9

ENV PYTHONUNBUFFERED 1

WORKDIR /app

COPY requirements.txt /app/
RUN pip install -r requirements.txt

COPY . /app/
COPY wait-for-it.sh /app/wait-for-it.sh

# Garante que o script está no formato UNIX e pode ser executado
RUN apt-get update && apt-get install -y dos2unix
RUN dos2unix /app/wait-for-it.sh
RUN chmod +x /app/wait-for-it.sh

CMD ["dos2unix /app/wait-for-it.sh"]
CMD ["chmod +x /app/wait-for-it.sh"]

# Startando o container com scrypt que aguarda o container do mysql subir primeiro.
CMD ["sh", "-c", "/app/wait-for-it.sh mysql:3306 --strict --timeout=40 -- python manage.py migrate && python manage.py runserver 0.0.0.0:8000"]

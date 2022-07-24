FROM python:3.8

WORKDIR /api

COPY . .

RUN pip3 install -r requirements.txt 

EXPOSE 5000

CMD ["uwsgi", "app.ini"]

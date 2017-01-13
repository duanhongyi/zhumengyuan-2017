FROM uucin/python:2.7
MAINTAINER duanhongyi <duanhongyi@zhumengyuan.com>

ADD . /app
WORKDIR /app

RUN pip install -r requirements.txt
ENV C_FORCE_ROOT 1
CMD celery -A tasks worker --loglevel=error --concurrency=1 & gunicorn -b 0.0.0.0:5000 app:app
EXPOSE 5000

FROM python:3.8

RUN pip install Flask requests psycopg2 psycogreen uwsgi gevent

COPY app.py /app.py
COPY patched.py /patched.py

CMD uwsgi --master \
  --single-interpreter \
  --workers $WORKERS \
  --gevent $ASYNC_CORES \
  --protocol http \
  --socket 0.0.0.0:$PORT_APP \
  --module $MODULE:app


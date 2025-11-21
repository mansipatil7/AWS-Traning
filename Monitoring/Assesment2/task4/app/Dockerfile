FROM python:3.9-slim

WORKDIR /app

COPY app.py .

CMD ["python3", "app.py"]



####################################


FROM python:3.9-alpine

WORKDIR /app

COPY app.py .

RUN adduser -D myuser
USER myuser

CMD ["python3", "app.py"]
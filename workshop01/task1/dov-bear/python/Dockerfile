# Creating the Dockerfile
FROM python:3.10-slim

LABEL name=myapp

ARG APP_DIR=/app

WORKDIR ${APP_DIR}

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY main.py utils.py run.sh ./
COPY public public
COPY templates templates

ENV PORT=3000
ENV INSTANCE_NAME="dov bear"
ENV INSTANCE_HASH="arbitrary"

EXPOSE ${PORT}

ENTRYPOINT ["./run.sh"]
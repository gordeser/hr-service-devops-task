FROM python:3.10-bullseye

EXPOSE 8000

WORKDIR /app

COPY requirements.txt /app

RUN pip install -r requirements.txt --no-cache-dir

COPY . /app

EXPOSE 8000

ENTRYPOINT [ "./entrypoint.sh" ]
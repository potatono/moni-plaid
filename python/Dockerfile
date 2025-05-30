FROM ubuntu:latest

WORKDIR /opt/app
COPY . .
WORKDIR /opt/app/python

RUN apt-get update
RUN apt-get install -y build-essential
RUN apt-get install -y python3 python3-pip

RUN pip3 install --break-system-packages -r requirements.txt

ENV FLASK_APP=/opt/app/python/server.py
EXPOSE 8000

#ENTRYPOINT ["sleep"]
#CMD ["10000000"]
ENTRYPOINT ["python3"]
CMD ["-m", "flask", "run", "--host=0.0.0.0", "--port=8000"]

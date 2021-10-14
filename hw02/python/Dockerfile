FROM ubuntu
RUN apt update
RUN apt install python3 -y
WORKDIR /app
COPY hello.py .
CMD ["python3", "-u", "hello.py"]
FROM ubuntu
RUN apt update
RUN apt install nodejs -y
WORKDIR /app
COPY hello.js .
CMD ["node", "hello.js"]
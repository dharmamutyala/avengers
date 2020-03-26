FROM launcher.gcr.io/google/nodejs
COPY . /app/
WORKDIR /app
RUN npm install
ENV SERVER=https://8080-dot-11362070-dot-devshell.appspot.com/
CMD ["node","server.js"]
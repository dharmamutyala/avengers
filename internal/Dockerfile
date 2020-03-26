FROM launcher.gcr.io/google/nodejs
COPY . /app/
WORKDIR /app
RUN npm install
EXPOSE 8082
CMD ["node", "server.js"]
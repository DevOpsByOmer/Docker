FROM node:14 AS build_img
WORKDIR /usr/src/app/
COPY ./ ./nodeapi
RUN cd nodeapi && npm install

FROM node:14
WORKDIR /usr/src/app/
COPY --from=build_img /usr/src/app/nodeapi/ ./
EXPOSE 5000
CMD ["/bin/bash", "-c", "cd /usr/src/app/ && npm start"]
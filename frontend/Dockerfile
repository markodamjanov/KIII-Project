FROM node:16-alpine

WORKDIR /frontend

COPY . .

RUN npm ci --legacy-peer-deps
RUN npm run build
RUN npm install -g serve

EXPOSE 3000

CMD /bin/sh /frontend/env.sh env-config && serve /frontend/build
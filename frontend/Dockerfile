# Stage 1 #

FROM node:16 AS stg1

WORKDIR /sys-stats

COPY package.json .

RUN npm install

COPY . .

EXPOSE 3000

RUN npm run build

# Stage 2 #

FROM nginx:stable AS stg2

WORKDIR /usr/share/nginx/html

RUN rm -rf ./*

# Copies static resources from builder stage
COPY --from=stg1 /sys-stats/build .



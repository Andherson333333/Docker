# Etapa de construcción
FROM node:18 AS build-env
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm ci --omit=dev

# Etapa de producción
FROM node:current-alpine3.18
WORKDIR /usr/src/app
COPY --from=build-env /usr/src/app /usr/src/app
EXPOSE 4000
CMD ["npm", "run", "start"]

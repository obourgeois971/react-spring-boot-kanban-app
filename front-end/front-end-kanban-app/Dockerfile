# Dockerfile pour l'application ReactJS

# Étape 1 : Construire l'application React
FROM node:14 AS build
WORKDIR /app
COPY . /app
RUN npm install && npm run build

# Étape 2 : Servir l'application avec Nginx
FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]

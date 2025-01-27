# # Use official Node.js image
# FROM node:18 AS build
# WORKDIR /app
# COPY frontend/package.json frontend/package-lock.json ./
# RUN npm install
# COPY frontend/ .
# RUN npm run build -- --configuration production

# # Use Nginx to serve the Angular app
# FROM nginx:alpine
# COPY --from=build /app/dist/frontend /usr/share/nginx/html
# COPY nginx/nginx.conf /etc/nginx/conf.d/default.conf
# EXPOSE 80

FROM hello-world
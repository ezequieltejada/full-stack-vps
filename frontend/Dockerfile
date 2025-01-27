# Use official Node.js image for building the Angular app
FROM node:18 AS build

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package.json package-lock.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Build the Angular app for production
RUN npm run build -- --configuration production

# Use Nginx to serve the Angular app
FROM nginx:alpine

# Copy the built Angular app from the build stage to the Nginx HTML directory
COPY --from=build /app/dist/frontend/browser /usr/share/nginx/html

# Copy the custom Nginx configuration file (if needed)
# COPY nginx/nginx.conf /etc/nginx/conf.d/default.conf

# Expose port 80 for the Nginx server
EXPOSE 80

# Start Nginx when the container starts
CMD ["nginx", "-g", "daemon off;"]
# Use an official Node.js image for the build
FROM node:16 AS build

# Set the working directory in the container
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the React application
COPY . .

# Build the React app for production
RUN npm run build

# Use an Nginx image to serve the static files
FROM nginx:alpine

# Copy the React build folder to Nginx's html directory
COPY --from=build /app/build /usr/share/nginx/html

# Copy the custom nginx.conf to the container
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Expose port 80 for the frontend
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]

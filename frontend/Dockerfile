# Use Node.js to build the React app
FROM node:18-alpine as build

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json to install dependencies
COPY package*.json ./

# Install frontend dependencies
RUN npm install

# Copy the rest of the frontend source code
COPY . .

# Build the React app for production
RUN npm run build 

# Check if the build folder was created
RUN ls -la /app

# Use NGINX to serve the built React app
FROM nginx:alpine

# Copy the built React app from the build stage
COPY --from=build /app/dist /usr/share/nginx/html

# Expose port 80 for the NGINX server
EXPOSE 80

# Start NGINX to serve the app
CMD ["nginx", "-g", "daemon off;"]


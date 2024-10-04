# Use an official Node.js runtime as the base image
FROM node:18-alpine

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json to install dependencies
COPY package*.json ./

# Install backend dependencies
RUN npm install

# Copy the rest of the backend source code
COPY . .

# Expose the backend API port
EXPOSE 5000

# Start the backend server
CMD ["npm", "start"]


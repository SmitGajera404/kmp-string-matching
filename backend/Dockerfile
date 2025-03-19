# Use an official Node.js image as the base image
FROM node:latest

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package.json package-lock.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application files
COPY . .

# Install nodemon globally
RUN npm install -g nodemon

# Expose the application port
EXPOSE 5000

# Start the app using nodemon
CMD ["nodemon", "server.js"]
